PS C:\GTPS\Gurotopia> $files = Get-ChildItem . -Recurse -File -Include *.cpp,*.hpp,*.h,*.cc |
>>     Where-Object {
>>         $_.FullName -notmatch '\\(\.git|build|bin|obj|vendor)\\'
>>     }
PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> $files |
>>     Select-String -Pattern '\b(OWNER|DEVELOPER|MODERATOR|PLAYER)\b|peer_is_(super_)?staff_role|(?:->|\.)role\b' |
>>     Format-Table Path,LineNumber,Line -Wrap

Path                                                            LineNumber Line
----                                                            ---------- ----
C:\GTPS\Gurotopia\include\action\dialog_return\gateway_edit.cpp         16     if (world->owner != 0 && world->owner !=
                                                                            pPeer->user_id && std::ranges::find(world->
                                                                           access, pPeer->user_id) == world->access.end
                                                                           ()) return; // @note same rule as building h
                                                                           ere
C:\GTPS\Gurotopia\include\action\dialog_return\lock_edit.cpp            14     if (world->owner != pPeer->user_id) retu
                                                                           rn; // @note only the owner can change the l
                                                                           ock
C:\GTPS\Gurotopia\include\action\join_request.cpp                       20         if (world.owner <= 0) return;
C:\GTPS\Gurotopia\include\action\join_request.cpp                       23         ::peer owner{.user_id = world.owner}
                                                                           ;
C:\GTPS\Gurotopia\include\action\join_request.cpp                       25         const bool granted = (pPeer->user_id
                                                                            == world.owner || std::ranges::find(world.a
                                                                           ccess, pPeer->user_id) != world.access.end()
                                                                           );
C:\GTPS\Gurotopia\include\action\join_request.cpp                       27             owner.mysql_select<std::string>(
                                                                           "growid", "", true), granted ? " (`2ACCESS G
                                                                           RANTED``)" : ""));
C:\GTPS\Gurotopia\include\action\join_request.cpp                       70         if (pPeer->user_id == world.owner)
C:\GTPS\Gurotopia\include\action\join_request.cpp                       90                                      peer_is_staff_role(pOthers->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp                       91                                      peer_is_super_staff_role(pOthers->role)
                                                                           ,
C:\GTPS\Gurotopia\include\action\join_request.cpp                      100                                      peer_is_staff_role(pPeer->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp                      101                                      peer_is_super_staff_role(pPeer->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp                      119                      peer_is_staff_role(pPeer->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp                      120                      peer_is_super_staff_role(pPeer->role),
C:\GTPS\Gurotopia\include\action\join_request.cpp                      154         on::ConsoleMessage(event.peer, exc.w
                                                                           hat()); // @note tell the player why
C:\GTPS\Gurotopia\include\action\wrench.cpp                             97                             .add_button("ign
                                                                           ore_player", "`wIgnore Player``")
C:\GTPS\Gurotopia\include\action\wrench.cpp                             98                             .add_button("rep
                                                                           ort_player", "`wReport Player``")
C:\GTPS\Gurotopia\include\commands\msg.cpp                              30                 send_gameMessage(event.peer,
                                                                            {.message = "action|log\n`6>> `4SYSTEM``: S
                                                                           orry! This player has ignored private messag
                                                                           es from non-friends. Become friends to chat!
                                                                           "});
C:\GTPS\Gurotopia\include\database\database.cpp                         30         "owner INT DEFAULT 0,"
C:\GTPS\Gurotopia\include\database\items.cpp                           206                 // @todo add the string for
                                                                           the player punch FX
C:\GTPS\Gurotopia\include\database\peer.cpp                             86 template std::string peer::mysql_select<std:
                                                                           :string>(const std::string&, const std::stri
                                                                           ng&, bool); // @note tile_change.cpp (World
                                                                           Lock owner name)
C:\GTPS\Gurotopia\include\database\peer.cpp                             96      this->role = static_cast<u_char>(role_value
                                                                           );
C:\GTPS\Gurotopia\include\database\peer.cpp                            154      const unsigned role_value = static_cast<uns
                                                                           igned>(this->role);
C:\GTPS\Gurotopia\include\database\peer.hpp                             62 constexpr bool peer_is_staff_role(u_char val
                                                                           ue) noexcept
C:\GTPS\Gurotopia\include\database\peer.hpp                             64     return value == OWNER ||
C:\GTPS\Gurotopia\include\database\peer.hpp                             65            value == DEVELOPER ||
C:\GTPS\Gurotopia\include\database\peer.hpp                             66            value == MODERATOR;
C:\GTPS\Gurotopia\include\database\peer.hpp                             69 constexpr bool peer_is_super_staff_role(u_ch
                                                                           ar value) noexcept
C:\GTPS\Gurotopia\include\database\peer.hpp                             71     return value == OWNER || value == DEVELO
                                                                           PER;
C:\GTPS\Gurotopia\include\database\peer.hpp                             74     OWNER     = 0,
C:\GTPS\Gurotopia\include\database\peer.hpp                             75     DEVELOPER = 1,
C:\GTPS\Gurotopia\include\database\peer.hpp                             76     MODERATOR = 2,
C:\GTPS\Gurotopia\include\database\peer.hpp                             77     PLAYER    = 3
C:\GTPS\Gurotopia\include\database\peer.hpp                            111     u_char role{PLAYER};
C:\GTPS\Gurotopia\include\database\peer.hpp                            244     ::pos speed{}; // @note player movement
                                                                           (velocity(x), gravity(y)), higher gravity =
                                                                           smaller jumps
C:\GTPS\Gurotopia\include\database\world.cpp                           140                 blob.i32(this->owner);
C:\GTPS\Gurotopia\include\database\world.cpp                           241     this->owner = this->mysql_select<int>("o
                                                                           wner");
C:\GTPS\Gurotopia\include\database\world.cpp                           324     this->mysql_update("owner", this->owner)
                                                                           ;
C:\GTPS\Gurotopia\include\database\world.cpp                           421     send_data(*event.peer, compress_state(ga
                                                                           mePacket)); // @note only the player whose b
                                                                           ackpack changes
C:\GTPS\Gurotopia\include\database\world.cpp                           528             blob.i32(world.owner);
C:\GTPS\Gurotopia\include\database\world.hpp                           151     int owner{ 00 }; // @note owner of world
                                                                            using peer's user id.
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                    41         if (!(item.cat & CAT_PUBLIC)) // @no
                                                                           te if block is public skip validating if pee
                                                                           r is owner or access
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                    42             if ((world->owner && !world->is_
                                                                           public && pPeer->role == PLAYER) &&
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                    43                 (pPeer->user_id != world->ow
                                                                           ner && std::ranges::find(world->access, pPee
                                                                           r->user_id) == world->access.end())) return;
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   129                     if (world->owner != pPee
                                                                           r->user_id)
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   131                         ::peer owner{}; // @
                                                                           note offline "fake" peer, only used to read
                                                                           the owner's name
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   132                         owner.user_id = worl
                                                                           d->owner;
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   133                         throw std::runtime_e
                                                                           rror(std::format("`5[```w{}`` `$World Locked
                                                                           `` by `w{}```5]``", world->name, owner.mysql
                                                                           _select<std::string>("growid", "", true)));
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   277                 world->owner = 0; // @todo h
                                                                           ave a seperate thing for 'range_lock'
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   432                             .add_textbox("En
                                                                           ter a message you want to broadcast to every
                                                                            player in Growtopia! This will use up 1 Meg
                                                                           aphone")
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   522                     if (pPeer->user_id == wo
                                                                           rld->owner)
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   719                     if (!world->owner)
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   721                         world->owner = pPeer
                                                                           ->user_id;
C:\GTPS\Gurotopia\include\gamePacket\tile_change.cpp                   774                 .netid = world->owner,
