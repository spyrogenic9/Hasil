PS C:\GTPS\Gurotopia> Get-Item .\main.exe,
>>          .\include\database\peer.cpp,
>>          .\include\database\peer.hpp,
>>          .\include\database\database.cpp |
>>     Select-Object Name, LastWriteTime, Length |
>>     Format-Table -AutoSize

Name         LastWriteTime                 Length
----         -------------                 ------
main.exe     Rabu, 11, 11, 2026 04.12.38 23146090
peer.cpp     Rabu, 11, 11, 2026 04.10.41    10951
peer.hpp     Rabu, 11, 11, 2026 04.05.23     7362
database.cpp Rabu, 11, 11, 2026 04.06.45     6517


PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> # 2. Cari seluruh implementasi dan pemeriksaan role
PS C:\GTPS\Gurotopia> Get-ChildItem -Recurse -File -Include *.cpp,*.hpp |
>>     Select-String -Pattern '\bOWNER\b|\bDEVELOPER\b|\bMODERATOR\b|\bPLAYER\b|\.role\b|->role\b' |
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
C:\GTPS\Gurotopia\include\action\join_request.cpp                       84                 on::Spawn(*event.peer, pOthe
                                                                           rs->netid, pOthers->user_id, pOthers->pos, p
                                                                           Others->display_growid, pOthers->country, pO
                                                                           thers->role, pOthers->role >= DEVELOPER, fal
                                                                           se);
C:\GTPS\Gurotopia\include\action\join_request.cpp                       85                 on::Spawn(*peer, pPeer->neti
                                                                           d, pPeer->user_id, pPeer->rest_pos, pPeer->d
                                                                           isplay_growid, pPeer->country, pPeer->role,
                                                                           pPeer->role >= DEVELOPER, false);
C:\GTPS\Gurotopia\include\action\join_request.cpp                       96         on::Spawn(*event.peer, pPeer->netid,
                                                                            pPeer->user_id, pPeer->rest_pos, pPeer->dis
                                                                           play_growid, pPeer->country, pPeer->role, pP
                                                                           eer->role >= DEVELOPER, true);
C:\GTPS\Gurotopia\include\action\join_request.cpp                      129         on::ConsoleMessage(event.peer, exc.w
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
C:\GTPS\Gurotopia\include\database\peer.hpp                             63     OWNER     = 0,
C:\GTPS\Gurotopia\include\database\peer.hpp                             64     DEVELOPER = 1,
C:\GTPS\Gurotopia\include\database\peer.hpp                             65     MODERATOR = 2,
C:\GTPS\Gurotopia\include\database\peer.hpp                             66     PLAYER    = 3
C:\GTPS\Gurotopia\include\database\peer.hpp                            100     u_char role{PLAYER};
C:\GTPS\Gurotopia\include\database\peer.hpp                            233     ::pos speed{}; // @note player movement
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
                                                                           public && !pPeer->role) &&
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


PS C:\GTPS\Gurotopia>
PS C:\GTPS\Gurotopia> # 3. Periksa proses server yang sedang berjalan
PS C:\GTPS\Gurotopia> Get-CimInstance Win32_Process -Filter "Name='main.exe'" |
>>     Select-Object ProcessId,ExecutablePath,CommandLine

ProcessId ExecutablePath             CommandLine
--------- --------------             -----------
    10384 C:\GTPS\Gurotopia\main.exe C:\GTPS\Gurotopia\main.exe
