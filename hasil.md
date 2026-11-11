PS C:\GTPS\Gurotopia> Write-Host "`n===== ALL ROLE REFERENCES ====="

===== ALL ROLE REFERENCES =====
PS C:\GTPS\Gurotopia> Get-ChildItem .\include -Recurse -File |
>>     Select-String -Pattern '\b(OWNER|DEVELOPER|MODERATOR|PLAYER|role|mstate|smstate)\b' |
>>     Select-Object Path, LineNumber, Line

Path                                                            LineNumber Line
----                                                            ---------- ----
C:\GTPS\Gurotopia\include\action\join_request.cpp                       20         if (world.owner <= 0) return;
C:\GTPS\Gurotopia\include\action\join_request.cpp                       23         ::peer owner{.user_id = world.own...
C:\GTPS\Gurotopia\include\action\join_request.cpp                       25         const bool granted = (pPeer->user...
C:\GTPS\Gurotopia\include\action\join_request.cpp                       27             owner.mysql_select<std::strin...
C:\GTPS\Gurotopia\include\action\join_request.cpp                       70         if (pPeer->user_id == world.owner)
C:\GTPS\Gurotopia\include\action\join_request.cpp                       90                                      peer_is_staff_role(pOthers->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp                       91                                      peer_is_super_staff_role(pOthers->ro...
C:\GTPS\Gurotopia\include\action\join_request.cpp                      100                                      peer_is_staff_role(pPeer->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp                      101                                      peer_is_super_staff_role(pPeer->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp                      119                      peer_is_staff_role(pPeer->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp                      120                      peer_is_super_staff_role(pPeer->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp                      154         on::ConsoleMessage(event.peer, ex...
C:\GTPS\Gurotopia\include\action\wrench.cpp                             97                             .add_button("...
C:\GTPS\Gurotopia\include\action\wrench.cpp                             98                             .add_button("...
C:\GTPS\Gurotopia\include\action\dialog_return\gateway_edit.cpp         16     if (world->owner != 0 && world->owner...
C:\GTPS\Gurotopia\include\action\dialog_return\lock_edit.cpp            14     if (world->owner != pPeer->user_id) r...
C:\GTPS\Gurotopia\include\commands\msg.cpp                              30                 send_gameMessage(event.pe...
C:\GTPS\Gurotopia\include\database\database.cpp                         19              "role TINYINT UNSIGNED NOT NULL DEFAULT...
C:\GTPS\Gurotopia\include\database\database.cpp                         30         "owner INT DEFAULT 0,"
C:\GTPS\Gurotopia\include\database\database.cpp                         63      if (!column_found("peer", "role")) alter...
C:\GTPS\Gurotopia\include\database\items.cpp                           206                 // @todo add the string f...
C:\GTPS\Gurotopia\include\database\peer.cpp                             87 template std::string peer::mysql_select<s...
C:\GTPS\Gurotopia\include\database\peer.cpp                             95              this->mysql_select<unsigned>("role", ""...
C:\GTPS\Gurotopia\include\database\peer.cpp                             97      this->role = static_cast<u_char>(role_va...
C:\GTPS\Gurotopia\include\database\peer.cpp                             98      std::cout << "[ROLE DEBUG] " << this->gr...
C:\GTPS\Gurotopia\include\database\peer.cpp                             99           << " | DB role=" << role_value
C:\GTPS\Gurotopia\include\database\peer.cpp                            100           << " | loaded role=" << static_...
C:\GTPS\Gurotopia\include\database\peer.cpp                            155     "xp = ?, wl_storage = ?, role = ? WHE...
C:\GTPS\Gurotopia\include\database\peer.cpp                            159      const unsigned role_value = static_cast<...
C:\GTPS\Gurotopia\include\database\peer.hpp                             61 enum role : u_char
C:\GTPS\Gurotopia\include\database\peer.hpp                             63     OWNER     = 0,
C:\GTPS\Gurotopia\include\database\peer.hpp                             64     DEVELOPER = 1,
C:\GTPS\Gurotopia\include\database\peer.hpp                             65     MODERATOR = 2,
C:\GTPS\Gurotopia\include\database\peer.hpp                             66     PLAYER    = 3
C:\GTPS\Gurotopia\include\database\peer.hpp                             71     return value == OWNER ||
C:\GTPS\Gurotopia\include\database\peer.hpp                             72            value == DEVELOPER ||
C:\GTPS\Gurotopia\include\database\peer.hpp                             73            value == MODERATOR;
C:\GTPS\Gurotopia\include\database\peer.hpp                             78     return value == OWNER || value == DEV...
C:\GTPS\Gurotopia\include\database\peer.hpp                            112     u_char role{PLAYER};
C:\GTPS\Gurotopia\include\database\peer.hpp                            245     ::pos speed{}; // @note player moveme...
C:\GTPS\Gurotopia\include\database\world.cpp                           140                 blob.i32(this->owner);
C:\GTPS\Gurotopia\include\database\world.cpp                           241     this->owner = this->mysql_select<int>...
C:\GTPS\Gurotopia\include\database\world.cpp                           324     this->mysql_update("owner", this->own...
C:\GTPS\Gurotopia\include\database\world.cpp                           421     send_data(*event.peer, compress_state...
C:\GTPS\Gurotopia\include\database\world.cpp                           528             blob.i32(world.owner);
C:\GTPS\Gurotopia\include\database\world.hpp                           151     int owner{ 00 }; // @note owner of wo...
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                    41         if (!(item.cat & CAT_PUBLIC)) // ...
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                    42             if ((world->owner && !world->...
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                    43                 (pPeer->user_id != world-...
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   129                     if (world->owner != p...
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   131                         ::peer owner{}; /...
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   132                         owner.user_id = w...
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   133                         throw std::runtim...
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   277                 world->owner = 0; // @tod...
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   432                             .add_textbox(...
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   522                     if (pPeer->user_id ==...
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   719                     if (!world->owner)
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   721                         world->owner = pP...
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   774                 .netid = world->owner,
C:\GTPS\Gurotopia\include\onVariant\Spawn.cpp                            5 void on::Spawn(ENetPeer &peer, signed net...
C:\GTPS\Gurotopia\include\onVariant\Spawn.cpp                           11             netID, userID, posXY.by_32(tr...
C:\GTPS\Gurotopia\include\onVariant\Spawn.hpp                            5     extern void Spawn(ENetPeer &peer, sig...


PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== ALL COMMAND FILES ====="

===== ALL COMMAND FILES =====
PS C:\GTPS\Gurotopia> Get-ChildItem .\include\commands -Recurse -File |
>>     Select-Object FullName

FullName
--------
C:\GTPS\Gurotopia\include\commands\find.cpp
C:\GTPS\Gurotopia\include\commands\find.hpp
C:\GTPS\Gurotopia\include\commands\ghost.cpp
C:\GTPS\Gurotopia\include\commands\ghost.hpp
C:\GTPS\Gurotopia\include\commands\me.cpp
C:\GTPS\Gurotopia\include\commands\me.hpp
C:\GTPS\Gurotopia\include\commands\msg.cpp
C:\GTPS\Gurotopia\include\commands\msg.hpp
C:\GTPS\Gurotopia\include\commands\news.cpp
C:\GTPS\Gurotopia\include\commands\news.hpp
C:\GTPS\Gurotopia\include\commands\punch.cpp
C:\GTPS\Gurotopia\include\commands\punch.hpp
C:\GTPS\Gurotopia\include\commands\sb.cpp
C:\GTPS\Gurotopia\include\commands\sb.hpp
C:\GTPS\Gurotopia\include\commands\skin.cpp
C:\GTPS\Gurotopia\include\commands\skin.hpp
C:\GTPS\Gurotopia\include\commands\time.cpp
C:\GTPS\Gurotopia\include\commands\time.hpp
C:\GTPS\Gurotopia\include\commands\warp.cpp
C:\GTPS\Gurotopia\include\commands\warp.hpp
C:\GTPS\Gurotopia\include\commands\weather.cpp
C:\GTPS\Gurotopia\include\commands\weather.hpp
C:\GTPS\Gurotopia\include\commands\who.cpp
C:\GTPS\Gurotopia\include\commands\who.hpp
C:\GTPS\Gurotopia\include\commands\__command.cpp
C:\GTPS\Gurotopia\include\commands\__command.hpp


PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> Write-Host "`n===== ACTION MODULES ====="

===== ACTION MODULES =====
PS C:\GTPS\Gurotopia> Get-ChildItem .\include\action -Recurse -File |
>>     Select-Object FullName

FullName
--------
C:\GTPS\Gurotopia\include\action\buy.cpp
C:\GTPS\Gurotopia\include\action\buy.hpp
C:\GTPS\Gurotopia\include\action\dialog_return.cpp
C:\GTPS\Gurotopia\include\action\dialog_return.hpp
C:\GTPS\Gurotopia\include\action\drop.cpp
C:\GTPS\Gurotopia\include\action\drop.hpp
C:\GTPS\Gurotopia\include\action\enter_game.cpp
C:\GTPS\Gurotopia\include\action\enter_game.hpp
C:\GTPS\Gurotopia\include\action\friends.cpp
C:\GTPS\Gurotopia\include\action\friends.hpp
C:\GTPS\Gurotopia\include\action\info.cpp
C:\GTPS\Gurotopia\include\action\info.hpp
C:\GTPS\Gurotopia\include\action\input.cpp
C:\GTPS\Gurotopia\include\action\input.hpp
C:\GTPS\Gurotopia\include\action\inventoryfavuitrigger.cpp
C:\GTPS\Gurotopia\include\action\inventoryfavuitrigger.hpp
C:\GTPS\Gurotopia\include\action\itemfavourite.cpp
C:\GTPS\Gurotopia\include\action\itemfavourite.hpp
C:\GTPS\Gurotopia\include\action\join_request.cpp
C:\GTPS\Gurotopia\include\action\join_request.hpp
C:\GTPS\Gurotopia\include\action\mod_trade.cpp
C:\GTPS\Gurotopia\include\action\mod_trade.hpp
C:\GTPS\Gurotopia\include\action\protocol.cpp
C:\GTPS\Gurotopia\include\action\protocol.hpp
C:\GTPS\Gurotopia\include\action\quit.cpp
C:\GTPS\Gurotopia\include\action\quit.hpp
C:\GTPS\Gurotopia\include\action\quit_to_exit.cpp
C:\GTPS\Gurotopia\include\action\quit_to_exit.hpp
C:\GTPS\Gurotopia\include\action\refresh_item_data.cpp
C:\GTPS\Gurotopia\include\action\refresh_item_data.hpp
C:\GTPS\Gurotopia\include\action\rem_trade.cpp
C:\GTPS\Gurotopia\include\action\rem_trade.hpp
C:\GTPS\Gurotopia\include\action\respawn.cpp
C:\GTPS\Gurotopia\include\action\respawn.hpp
C:\GTPS\Gurotopia\include\action\respawn_spike.cpp
C:\GTPS\Gurotopia\include\action\respawn_spike.hpp
C:\GTPS\Gurotopia\include\action\setSkin.cpp
C:\GTPS\Gurotopia\include\action\setSkin.hpp
C:\GTPS\Gurotopia\include\action\store.cpp
C:\GTPS\Gurotopia\include\action\store.hpp
C:\GTPS\Gurotopia\include\action\storenavigate.cpp
C:\GTPS\Gurotopia\include\action\storenavigate.hpp
C:\GTPS\Gurotopia\include\action\tankIDName.cpp
C:\GTPS\Gurotopia\include\action\tankIDName.hpp
C:\GTPS\Gurotopia\include\action\trade_started.cpp
C:\GTPS\Gurotopia\include\action\trade_started.hpp
C:\GTPS\Gurotopia\include\action\trash.cpp
C:\GTPS\Gurotopia\include\action\trash.hpp
C:\GTPS\Gurotopia\include\action\validate_world.cpp
C:\GTPS\Gurotopia\include\action\validate_world.hpp
C:\GTPS\Gurotopia\include\action\worldlock_storage_getpage.cpp
C:\GTPS\Gurotopia\include\action\worldlock_storage_getpage.hpp
C:\GTPS\Gurotopia\include\action\worldlock_storage_modify_amount.cpp
C:\GTPS\Gurotopia\include\action\worldlock_storage_modify_amount.hpp
C:\GTPS\Gurotopia\include\action\wrench.cpp
C:\GTPS\Gurotopia\include\action\wrench.hpp
C:\GTPS\Gurotopia\include\action\__action.cpp
C:\GTPS\Gurotopia\include\action\__action.hpp
C:\GTPS\Gurotopia\include\action\dialog_return\billboard_edit.cpp
C:\GTPS\Gurotopia\include\action\dialog_return\billboard_edit.hpp
C:\GTPS\Gurotopia\include\action\dialog_return\create_blast.cpp
C:\GTPS\Gurotopia\include\action\dialog_return\create_blast.hpp
C:\GTPS\Gurotopia\include\action\dialog_return\drop_item.cpp
C:\GTPS\Gurotopia\include\action\dialog_return\drop_item.hpp
C:\GTPS\Gurotopia\include\action\dialog_return\find_item.cpp
C:\GTPS\Gurotopia\include\action\dialog_return\find_item.hpp
C:\GTPS\Gurotopia\include\action\dialog_return\gateway_edit.cpp
C:\GTPS\Gurotopia\include\action\dialog_return\gateway_edit.hpp
C:\GTPS\Gurotopia\include\action\dialog_return\lock_edit.cpp
C:\GTPS\Gurotopia\include\action\dialog_return\lock_edit.hpp
C:\GTPS\Gurotopia\include\action\dialog_return\megaphone.cpp
C:\GTPS\Gurotopia\include\action\dialog_return\megaphone.hpp
C:\GTPS\Gurotopia\include\action\dialog_return\popup.cpp
C:\GTPS\Gurotopia\include\action\dialog_return\popup.hpp
C:\GTPS\Gurotopia\include\action\dialog_return\socialportal.cpp
C:\GTPS\Gurotopia\include\action\dialog_return\socialportal.hpp
C:\GTPS\Gurotopia\include\action\dialog_return\trade_item.cpp
C:\GTPS\Gurotopia\include\action\dialog_return\trade_item.hpp
C:\GTPS\Gurotopia\include\action\dialog_return\trash_item.cpp
C:\GTPS\Gurotopia\include\action\dialog_return\trash_item.hpp
C:\GTPS\Gurotopia\include\action\dialog_return\__dialog_return.cpp
C:\GTPS\Gurotopia\include\action\dialog_return\__dialog_return.hpp
