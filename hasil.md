===== CURRENT STORAGE HANDLER =====
PS C:\GTPS\Gurotopia> Get-Content .\include\action\worldlock_storage_modify_amount.cpp

#include "pch.hpp"

#include <algorithm>
#include <charconv>
#include <limits>

#include "onVariant/ConsoleMessage.hpp"
#include "onVariant/WorldLockStorageResponse.hpp"
#include "onVariant/EventButtonDataSet.hpp"
#include "tools/conversions.hpp"

#include "worldlock_storage_getpage.hpp"
#include "worldlock_storage_modify_amount.hpp"

void action::worldlock_storage_modify_amount(ENetEvent& event, const std::string& header)
{
    ::peer* pPeer = static_cast<::peer*>(event.peer->data);
    if (pPeer == nullptr) return;

    const ::hPipe hPipe{ header };

    // Strict integer parsing: reject malformed input and overflow.
    auto parse_integer = [](const std::string& text, int& value) -> bool
    {
        if (text.empty()) return false;

        const char* begin = text.data();
        const char* end = begin + text.size();

        const auto result = std::from_chars(begin, end, value);

        return result.ec == std::errc{} && result.ptr == end;
    };

    int amount{};
    int type{};

    if (!parse_integer(hPipe["amount"], amount) || amount <= 0)
        return;

    if (!parse_integer(hPipe["type"], type))
        return;

    if (type < -1 || type > 1)
        return;

    auto refresh_storage = [&]()
    {
        on::EventButtonDataSet(event, true);
        on::EventButtonDataSet(event, false);

        send_varlist(event.peer, {
            "OnActiveAuctionUpdate",
            "{\"Active\":false}"
        });

        on::WorldLockStorageResponse(event.peer);
    };

    // Preserve the existing refresh-only behavior.
    if (type == 0)
    {
        refresh_storage();
        return;
    }

    auto get_inventory_count = [&](short item_id, int& count) -> bool
    {
        const auto it = std::ranges::find(
            pPeer->slots,
            item_id,
            &::slot::id
        );

        count = (it == pPeer->slots.end())
            ? 0
            : static_cast<int>(it->count);

        return count >= 0 && count <= 200;
    };

    int owned_wl{};
    int owned_dl{};
    int owned_bgl{};

    if (!get_inventory_count(242, owned_wl))
        return;

    if (!get_inventory_count(1796, owned_dl))
        return;

    // The client uses 1100090 as the Store All request value.
    // It is a command sentinel, NOT the literal amount of WL.
    constexpr int STORE_ALL_AMOUNT = 1100090;

    const bool store_all =
        (type == 1 && amount == STORE_ALL_AMOUNT);

    // Resolve Store All using the actual server-side inventory.
    if (store_all)
    {
        const long long total_value =
            static_cast<long long>(owned_bgl) * BLUE_GEM_LOCK_VALUE +
            static_cast<long long>(owned_dl) * DIAMOND_LOCK_VALUE +
            static_cast<long long>(owned_wl);

        if (total_value > std::numeric_limits<int>::max())
            return;

        amount = static_cast<int>(total_value);
    }

    // Reject corrupted balances.
    if (pPeer->wl_storage < 0)
        return;

    // Empty Store All: do not modify the balance or inventory.
    // Still refresh the interface so the button does not appear stuck.
    if (amount <= 0)
    {
        if (store_all)
            refresh_storage();

        return;
    }

    // Validate balance after resolving the actual Store All amount.
    if (type == 1)
    {
        if (amount > std::numeric_limits<int>::max() - pPeer->wl_storage)
            return;
    }
    else
    {
        if (amount > pPeer->wl_storage)
            return;
    }

    // Deposit: available inventory counts.
    // Withdrawal: remaining capacity in each inventory stack.
    const int wl_capacity = (type == 1)
        ? owned_wl
        : 200 - owned_wl;

    const int dl_capacity = (type == 1)
        ? owned_dl
        : 200 - owned_dl;

    const int bgl_capacity = (type == 1)
        ? owned_bgl
        : 200 - owned_bgl;

    int bgl{};
    int dl{};
    int wl{};
    int remaining = amount;

    if (store_all)
    {
        // Store All must transfer every owned lock, not reconstruct
        // a requested denomination from the sentinel.
        bgl = owned_bgl;
        dl = owned_dl;
        wl = owned_wl;

        remaining = 0;
    }
    else
    {
        // Normal deposit / withdrawal denomination conversion.
        bgl = std::min<int>(
            remaining / BLUE_GEM_LOCK_VALUE,
            bgl_capacity
        );
        remaining -= bgl * BLUE_GEM_LOCK_VALUE;

        dl = std::min<int>(
            remaining / DIAMOND_LOCK_VALUE,
            dl_capacity
        );
        remaining -= dl * DIAMOND_LOCK_VALUE;

        wl = std::min<int>(
            remaining,
            wl_capacity
        );
        remaining -= wl;
    }

    // Never execute an incomplete transaction.
    if (remaining != 0)
        return;

    // All item counts are now verified to fit within signed short
    // and the inventory's 0..200 stack limit.
    std::string collected;

    if (bgl > 0)
    {
        collected = std::format(
            "{} `2Blue Gem Lock`` and {} `2Diamond Lock`` and {} `2World Lock``",
            bgl, dl, wl
        );
    }
    else if (dl > 0)
    {
        collected = std::format(
            "{} `2Diamond Lock`` and {} `2World Lock``",
            dl, wl
        );
    }
    else if (wl > 0)
    {
        collected = std::format(
            "{} `2World Lock``",
            wl
        );
    }

    const short direction = (type == 1) ? -1 : 1;

    // Apply inventory changes only after every validation has passed.
    if (bgl > 0)
    {
        modify_item_inventory(
            event,
            ::slot(7188, static_cast<short>(direction * bgl))
        );
    }

    if (dl > 0)
    {
        modify_item_inventory(
            event,
            ::slot(1796, static_cast<short>(direction * dl))
        );
    }

    if (wl > 0)
    {
        modify_item_inventory(
            event,
            ::slot(242, static_cast<short>(direction * wl))
        );
    }

    // Change the storage balance only after inventory changes.
    if (type == 1)
        pPeer->wl_storage += amount;
    else
        pPeer->wl_storage -= amount;

    if (type == -1)
    {
        const std::string message = std::format(
            "You collected {}.",
            collected
        );

        send_varlist(event.peer, {
            "OnTalkBubble",
            pPeer->netid,
            message,
            0u,
            1u
        });

        on::ConsoleMessage(event.peer, message);
    }

    refresh_storage();
}
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== CURRENT INVENTORY COUNTS ====="

===== CURRENT INVENTORY COUNTS =====
PS C:\GTPS\Gurotopia> Get-Content .\include\database\peer.cpp |
>>     Select-String -Pattern 'peer::emplace|peer::have_slot' -Context 0,22

> u_short peer::emplace(::slot slot)
  {
      auto it = std::ranges::find(this->slots, slot.id, &::slot::id);

      if (it != this->slots.end())
      {
          const u_short excess = std::max(0, (it->count + slot.count) - 200);
          it->count = std::min(it->count + slot.count, 200);
          if (it->count == 0)
          {
              const ::item &item = id_to_item(it->id);
              if (item.cloth_type != clothing::NONE) this->clothing[item.cloth_type] = 0;
          }
          return excess;
      }
      this->slots.emplace_back(std::move(slot)); // @note no such item in inventory, so we create a new entry.
      return 0;
  }

> u_short peer::have_slot(::slot slot)
  {
      auto it = std::ranges::find(this->slots, slot.id, &::slot::id);

      if (it != this->slots.end())
          return it->count;
      return 0;
  }

  void peer::add_xp(ENetEvent &event, u_short value)
  {
      u_short &lvl = this->level.front();
      u_short &xp = this->level.back() += value; // @note factor the new xp amount

      for (; lvl < 125; )
      {
          u_short xp_formula = 50 * (lvl * lvl + 2); // @author https://www.growtopiagame.com/forums/member/553046-kase
te
          if (xp < xp_formula) break;

          xp -= xp_formula;
          lvl++;

          if (lvl == 50)


PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== STORAGE ACTION REFERENCES ====="

===== STORAGE ACTION REFERENCES =====
PS C:\GTPS\Gurotopia> Get-ChildItem .\include -Recurse -File -Include *.cpp,*.hpp |
>>     Select-String -Pattern 'worldlock_storage_modify_amount|1100090' -Context 3,5

  include\action\worldlock_storage_modify_amount.cpp:11:#include "tools/conversions.hpp"
  include\action\worldlock_storage_modify_amount.cpp:12:
  include\action\worldlock_storage_modify_amount.cpp:13:#include "worldlock_storage_getpage.hpp"
> include\action\worldlock_storage_modify_amount.cpp:14:#include "worldlock_storage_modify_amount.hpp"
  include\action\worldlock_storage_modify_amount.cpp:15:
> include\action\worldlock_storage_modify_amount.cpp:16:void action::worldlock_storage_modify_amount(ENetEvent& event,
const std::string& header)
  include\action\worldlock_storage_modify_amount.cpp:17:{
  include\action\worldlock_storage_modify_amount.cpp:18:    ::peer* pPeer = static_cast<::peer*>(event.peer->data);
  include\action\worldlock_storage_modify_amount.cpp:19:    if (pPeer == nullptr) return;
  include\action\worldlock_storage_modify_amount.cpp:20:
  include\action\worldlock_storage_modify_amount.cpp:21:    const ::hPipe hPipe{ header };
  include\action\worldlock_storage_modify_amount.cpp:90:    if (!get_inventory_count(1796, owned_dl))
  include\action\worldlock_storage_modify_amount.cpp:91:        return;
  include\action\worldlock_storage_modify_amount.cpp:92:
> include\action\worldlock_storage_modify_amount.cpp:93:    // The client uses 1100090 as the Store All request value.
  include\action\worldlock_storage_modify_amount.cpp:94:    // It is a command sentinel, NOT the literal amount of WL.
> include\action\worldlock_storage_modify_amount.cpp:95:    constexpr int STORE_ALL_AMOUNT = 1100090;
  include\action\worldlock_storage_modify_amount.cpp:96:
  include\action\worldlock_storage_modify_amount.cpp:97:    const bool store_all =
  include\action\worldlock_storage_modify_amount.cpp:98:        (type == 1 && amount == STORE_ALL_AMOUNT);
  include\action\worldlock_storage_modify_amount.cpp:99:
  include\action\worldlock_storage_modify_amount.cpp:100:    // Resolve Store All using the actual server-side inventor
y.
  include\action\worldlock_storage_modify_amount.hpp:2:
  include\action\worldlock_storage_modify_amount.hpp:3:namespace action
  include\action\worldlock_storage_modify_amount.hpp:4:{
> include\action\worldlock_storage_modify_amount.hpp:5:    extern void worldlock_storage_modify_amount(ENetEvent& event
, const std::string& header);
  include\action\worldlock_storage_modify_amount.hpp:6:}
  include\action\__action.cpp:29:#include "buy.hpp"
  include\action\__action.cpp:30:
  include\action\__action.cpp:31:#include "worldlock_storage_getpage.hpp"
> include\action\__action.cpp:32:#include "worldlock_storage_modify_amount.hpp"
  include\action\__action.cpp:33:
  include\action\__action.cpp:34:#include "quit.hpp"
  include\action\__action.cpp:35:
  include\action\__action.cpp:36:#include "__action.hpp"
  include\action\__action.cpp:37:
  include\action\__action.cpp:66:    {"action|buy", std::bind(&action::buy, std::placeholders::_1, std::placeholders::_
2, "")},
  include\action\__action.cpp:67:
  include\action\__action.cpp:68:    {"action|worldlock_storage_getpage", std::bind(&action::worldlock_storage_getpage,
 std::placeholders::_1, std::placeholders::_2)},
> include\action\__action.cpp:69:    {"action|worldlock_storage_modify_amount", std::bind(&action::worldlock_storage_mo
dify_amount, std::placeholders::_1, std::placeholders::_2)},
  include\action\__action.cpp:70:
  include\action\__action.cpp:71:    {"action|quit", std::bind(&action::quit, std::placeholders::_1, std::placeholders:
:_2)}
  include\action\__action.cpp:72:};
