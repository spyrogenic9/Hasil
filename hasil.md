PS C:\WINDOWS\system32> $backupDir = "C:\GTPS_BACKUPS"
PS C:\WINDOWS\system32> $stamp = Get-Date -Format "yyyyMMdd_HHmmss"
PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> New-Item -ItemType Directory -Force -Path $backupDir | Out-Null
PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> $dbFile = "$backupDir\gurotopia_$stamp.sql"
PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> & mysqldump.exe `
>>     -u root `
>>     -p `
>>     --single-transaction `
>>     --routines `
>>     --events `
>>     --triggers `
>>     --databases gurotopia `
>>     --result-file="$dbFile"
& : The term 'mysqldump.exe' is not recognized as the name of a cmdlet, function, script file, or operable program. Che
ck the spelling of the name, or if a path was included, verify that the path is correct and try again.
At line:1 char:3
+ & mysqldump.exe `
+   ~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (mysqldump.exe:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> if ($LASTEXITCODE -ne 0) {
>>     throw "Database backup gagal!"
>> }
Database backup gagal!
At line:2 char:5
+     throw "Database backup gagal!"
+     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OperationStopped: (Database backup gagal!:String) [], RuntimeException
    + FullyQualifiedErrorId : Database backup gagal!

PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> Write-Host "Database backup berhasil: $dbFile" -ForegroundColor Green
Database backup berhasil: C:\GTPS_BACKUPS\gurotopia_20261112_030903.sql
PS C:\WINDOWS\system32> $source = "C:\GTPS"
PS C:\WINDOWS\system32> $destination = "$backupDir\Gurotopia_FULL_$stamp"
PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> New-Item -ItemType Directory -Force -Path $destination | Out-Null
PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> robocopy $source "$destination\GTPS" /E /COPY:DAT /DCOPY:DAT /R:2 /W:2 /XJ

-------------------------------------------------------------------------------
   ROBOCOPY     ::     Robust File Copy for Windows
-------------------------------------------------------------------------------

  Started : Kamis, 12 November 2026 03.09.16
   Source : C:\GTPS\
     Dest : C:\GTPS_BACKUPS\Gurotopia_FULL_20261112_030903\GTPS\

    Files : *.*

  Options : *.* /S /E /DCOPY:DAT /COPY:DAT /XJ /R:2 /W:2

------------------------------------------------------------------------------

          New Dir          2    C:\GTPS\
100%        New File                 409        Caddyfile
100%        New File                7052        Run_Server.bat
          New Dir          2    C:\GTPS\backups\
            New File                   0        gurotopia_20261111_040200.sql
100%        New File               95153        gurotopia_20261111_040212.sql
          New Dir         16    C:\GTPS\Gurotopia\
100%        New File                  17        .gitignore
100%        New File                 144        Dockerfile
100%        New File                  32        guest_secret.key
100%        New File               5.4 m        items.dat
100%        New File               1.1 m        libmariadb.dll
100%        New File               11357        LICENSE
100%        New File                1975        main.cpp
100%        New File              22.9 m        main.exe
100%        New File              22.0 m        main.exe.before-role-fix
100%        New File                 829        Makefile
100%        New File                  41        mysql_login.txt
100%        New File                5971        README.md
100%        New File                 169        server_data.php
100%        New File                4530        storage_trace.log
100%        New File                1029        windows-setup.bat
100%        New File                 206        worldlock_storage_debug.log
          New Dir          0    C:\GTPS\Gurotopia\.github\
          New Dir          1    C:\GTPS\Gurotopia\.github\workflows\
100%        New File                1797        make-gcc.yml
          New Dir          3    C:\GTPS\Gurotopia\.vscode\
100%        New File                 438        c_cpp_properties.json
100%        New File                 512        launch.json
100%        New File                 709        tasks.json
          New Dir          2    C:\GTPS\Gurotopia\build\
100%        New File                1584        main.d
100%        New File              188685        main.o
          New Dir          2    C:\GTPS\Gurotopia\build\include\
100%        New File                1208        pch.hpp.d
100%        New File             152.4 m        pch.hpp.gch
          New Dir         58    C:\GTPS\Gurotopia\build\include\action\
100%        New File                1482        buy.d
100%        New File             1002137        buy.o
100%        New File                1450        dialog_return.d
100%        New File              520701        dialog_return.o
100%        New File                1376        drop.d
100%        New File              438453        drop.o
100%        New File                1710        enter_game.d
100%        New File              453754        enter_game.o
100%        New File                1388        friends.d
100%        New File              165247        friends.o
100%        New File                1376        info.d
100%        New File              523840        info.o
100%        New File                1558        input.d
100%        New File              926811        input.o
100%        New File                1448        inventoryfavuitrigger.d
100%        New File              162027        inventoryfavuitrigger.o
100%        New File                1422        itemfavourite.d
100%        New File              369530        itemfavourite.o
100%        New File                1916        join_request.d
100%        New File               1.5 m        join_request.o
100%        New File                1396        mod_trade.d
100%        New File              437856        mod_trade.o
100%        New File                1442        protocol.d
100%        New File              461634        protocol.o
100%        New File                1376        quit.d
100%        New File              198281        quit.o
100%        New File                1514        quit_to_exit.d
100%        New File              984589        quit_to_exit.o
100%        New File                1442        refresh_item_data.d
100%        New File              142729        refresh_item_data.o
100%        New File                1400        rem_trade.d
100%        New File              230546        rem_trade.o
100%        New File                1322        respawn.d
100%        New File              235955        respawn.o
100%        New File                1346        respawn_spike.d
100%        New File              233892        respawn_spike.o
100%        New File                1392        setSkin.d
100%        New File              217507        setSkin.o
100%        New File                1310        store.d
100%        New File              357105        store.o
100%        New File                1394        storenavigate.d
100%        New File              171910        storenavigate.o
100%        New File                1448        tankIDName.d
100%        New File              481354        tankIDName.o
100%        New File                1346        trade_started.d
100%        New File              176858        trade_started.o
100%        New File                1380        trash.d
100%        New File              453209        trash.o
100%        New File                1350        validate_world.d
100%        New File              464827        validate_world.o
100%        New File                1494        worldlock_storage_getpage.d
100%        New File              147479        worldlock_storage_getpage.o
100%        New File                1844        worldlock_storage_modify_amount.d
100%        New File              676378        worldlock_storage_modify_amount.o
100%        New File                1384        wrench.d
100%        New File              569645        wrench.o
100%        New File                3158        __action.d
100%        New File               1.2 m        __action.o
          New Dir         24    C:\GTPS\Gurotopia\build\include\action\dialog_return\
100%        New File                1488        billboard_edit.d
100%        New File              255008        billboard_edit.o
100%        New File                1538        create_blast.d
100%        New File              321211        create_blast.o
100%        New File                1466        drop_item.d
100%        New File              440765        drop_item.o
100%        New File                1466        find_item.d
100%        New File              338546        find_item.o
100%        New File                1398        gateway_edit.d
100%        New File              534391        gateway_edit.o
100%        New File                1466        lock_edit.d
100%        New File              544591        lock_edit.o
100%        New File                1440        megaphone.d
100%        New File              199944        megaphone.o
100%        New File                1370        popup.d
100%        New File              898570        popup.o
100%        New File                1398        socialportal.d
100%        New File              278580        socialportal.o
100%        New File                1544        trade_item.d
100%        New File              356291        trade_item.o
100%        New File                1470        trash_item.d
100%        New File              480989        trash_item.o
100%        New File                2500        __dialog_return.d
100%        New File              712950        __dialog_return.o
          New Dir          2    C:\GTPS\Gurotopia\build\include\admin\
100%        New File                1714        admin.d
100%        New File               1.0 m        admin.o
          New Dir          2    C:\GTPS\Gurotopia\build\include\automate\
100%        New File                1330        holiday.d
100%        New File              141274        holiday.o
          New Dir         26    C:\GTPS\Gurotopia\build\include\commands\
100%        New File                1394        find.d
100%        New File              228179        find.o
100%        New File                1392        ghost.d
100%        New File              147314        ghost.o
100%        New File                1386        me.d
100%        New File              418282        me.o
100%        New File                1310        msg.d
100%        New File              437115        msg.o
100%        New File                1394        news.d
100%        New File               40576        news.o
100%        New File                1392        punch.d
100%        New File              212731        punch.o
100%        New File                1446        sb.d
100%        New File              453567        sb.o
100%        New File                1388        skin.d
100%        New File              223386        skin.o
100%        New File                1454        time.d
100%        New File              372867        time.o
100%        New File                1450        warp.d
100%        New File              323568        warp.o
100%        New File                1330        weather.d
100%        New File              171397        weather.o
100%        New File                1310        who.d
100%        New File              490656        who.o
100%        New File                2122        __command.d
100%        New File              511240        __command.o
          New Dir         10    C:\GTPS\Gurotopia\build\include\database\
100%        New File                1268        database.d
100%        New File              619715        database.o
100%        New File                1262        items.d
100%        New File              699164        items.o
100%        New File                1542        peer.d
100%        New File              830623        peer.o
100%        New File                1330        shouhin.d
100%        New File              385832        shouhin.o
100%        New File                1446        world.d
100%        New File               1.1 m        world.o
          New Dir          8    C:\GTPS\Gurotopia\build\include\eventType\
100%        New File                1334        connect.d
100%        New File              418679        connect.o
100%        New File                1396        disconnect.d
100%        New File              120812        disconnect.o
100%        New File                1468        receive.d
100%        New File              714434        receive.o
100%        New File                1542        _eventType.d
100%        New File               35407        _eventType.o
          New Dir         18    C:\GTPS\Gurotopia\build\include\gamePacket\
100%        New File                1400        disconnect.d
100%        New File              122054        disconnect.o
100%        New File                1572        item_activate.d
100%        New File              261596        item_activate.o
100%        New File                1534        item_activate_object.d
100%        New File              560545        item_activate_object.o
100%        New File                1398        movement.d
100%        New File              198876        movement.o
100%        New File                1350        ping_reply.d
100%        New File              344487        ping_reply.o
100%        New File                1366        set_icon_state.d
100%        New File              174405        set_icon_state.o
100%        New File                1498        tile_activate.d
100%        New File              396007        tile_activate.o
100%        New File                2178        tile_change.d
100%        New File               1.2 m        tile_change.o
100%        New File                1972        _gamePacket.d
100%        New File              340677        _gamePacket.o
          New Dir          4    C:\GTPS\Gurotopia\build\include\https\
100%        New File                1372        https.d
100%        New File              384814        https.o
100%        New File                1334        server_data.d
100%        New File              469669        server_data.o
          New Dir         28    C:\GTPS\Gurotopia\build\include\onVariant\
100%        New File                1330        Action.d
100%        New File              275646        Action.o
100%        New File                1366        BillboardChange.d
100%        New File              373137        BillboardChange.o
100%        New File                1362        ConsoleMessage.d
100%        New File              153830        ConsoleMessage.o
100%        New File                1354        CountryState.d
100%        New File              386723        CountryState.o
100%        New File                1382        EmoticonDataChanged.d
100%        New File              698290        EmoticonDataChanged.o
100%        New File                1378        EventButtonDataSet.d
100%        New File              316834        EventButtonDataSet.o
100%        New File                1350        NameChanged.d
100%        New File              377680        NameChanged.o
100%        New File                1492        RequestGazette.d
100%        New File              425897        RequestGazette.o
100%        New File                1474        RequestWorldSelectMenu.d
100%        New File              706374        RequestWorldSelectMenu.o
100%        New File                1330        SetBux.d
100%        New File              249132        SetBux.o
100%        New File                1350        SetClothing.d
100%        New File              239787        SetClothing.o
100%        New File                1326        Spawn.d
100%        New File              334402        Spawn.o
100%        New File                1350        TradeStatus.d
100%        New File              448559        TradeStatus.o
100%        New File                1402        WorldLockStorageResponse.d
100%        New File              263433        WorldLockStorageResponse.o
          New Dir          2    C:\GTPS\Gurotopia\build\include\proton\
100%        New File                1262        Variant.d
100%        New File              195089        Variant.o
          New Dir         12    C:\GTPS\Gurotopia\build\include\tools\
100%        New File                1334        conversions.d
100%        New File              292035        conversions.o
100%        New File                1342        create_dialog.d
100%        New File              448632        create_dialog.o
100%        New File                1310        random.d
100%        New File               24783        random.o
100%        New File                1258        string.d
100%        New File              237456        string.o
100%        New File                1262        terminal.d
100%        New File               35197        terminal.o
100%        New File                1302        time.d
100%        New File               24482        time.o
          New Dir          1    C:\GTPS\Gurotopia\include\
100%        New File                 401        pch.hpp
          New Dir         61    C:\GTPS\Gurotopia\include\action\
100%        New File                8250        buy.cpp
100%        New File                 136        buy.hpp
100%        New File                 414        dialog_return.cpp
100%        New File                 111        dialog_return.hpp
100%        New File                1076        drop.cpp
100%        New File                 103        drop.hpp
100%        New File                2155        enter_game.cpp
100%        New File                 109        enter_game.hpp
100%        New File                 760        friends.cpp
100%        New File                 106        friends.hpp
100%        New File                2426        info.cpp
100%        New File                 103        info.hpp
100%        New File                2736        input.cpp
100%        New File                 104        input.hpp
100%        New File                 690        inventoryfavuitrigger.cpp
100%        New File                 120        inventoryfavuitrigger.hpp
100%        New File                 874        itemfavourite.cpp
100%        New File                 112        itemfavourite.hpp
100%        New File                5979        join_request.cpp
100%        New File                 142        join_request.hpp
100%        New File                 921        mod_trade.cpp
100%        New File                 108        mod_trade.hpp
100%        New File                2560        protocol.cpp
100%        New File                 107        protocol.hpp
100%        New File                 405        quit.cpp
100%        New File                 103        quit.hpp
100%        New File                1582        quit_to_exit.cpp
100%        New File                 132        quit_to_exit.hpp
100%        New File                 362        refresh_item_data.cpp
100%        New File                 116        refresh_item_data.hpp
100%        New File                 532        rem_trade.cpp
100%        New File                 108        rem_trade.hpp
100%        New File                 590        respawn.cpp
100%        New File                 106        respawn.hpp
100%        New File                 440        respawn_spike.cpp
100%        New File                 112        respawn_spike.hpp
100%        New File                 508        setSkin.cpp
100%        New File                 106        setSkin.hpp
100%        New File                8364        store.cpp
100%        New File                 104        store.hpp
100%        New File                 492        storenavigate.cpp
100%        New File                 112        storenavigate.hpp
100%        New File                7707        tankIDName.cpp
100%        New File                 109        tankIDName.hpp
100%        New File                 171        trade_started.cpp
100%        New File                 105        trade_started.hpp
100%        New File                1200        trash.cpp
100%        New File                 104        trash.hpp
100%        New File                 401        validate_world.cpp
100%        New File                 112        validate_world.hpp
100%        New File                 308        worldlock_storage_getpage.cpp
100%        New File                 123        worldlock_storage_getpage.hpp
100%        New File                6929        worldlock_storage_modify_amount.cpp
100%        New File                8009        worldlock_storage_modify_amount.cpp.20261112_030104.bak
100%        New File                1745        worldlock_storage_modify_amount.cpp.bak
100%        New File                6539        worldlock_storage_modify_amount.cpp.before_storage_trace.bak
100%        New File                 129        worldlock_storage_modify_amount.hpp
100%        New File                7594        wrench.cpp
100%        New File                 105        wrench.hpp
100%        New File                3889        __action.cpp
100%        New File                 167        __action.hpp
          New Dir         24    C:\GTPS\Gurotopia\include\action\dialog_return\
100%        New File                 593        billboard_edit.cpp
100%        New File                  82        billboard_edit.hpp
100%        New File                1199        create_blast.cpp
100%        New File                  80        create_blast.hpp
100%        New File                2025        drop_item.cpp
100%        New File                  77        drop_item.hpp
100%        New File                1128        find_item.cpp
100%        New File                  77        find_item.hpp
100%        New File                2085        gateway_edit.cpp
100%        New File                  80        gateway_edit.hpp
100%        New File                1435        lock_edit.cpp
100%        New File                  77        lock_edit.hpp
100%        New File                 352        megaphone.cpp
100%        New File                  77        megaphone.hpp
100%        New File                3917        popup.cpp
100%        New File                  73        popup.hpp
100%        New File                1041        socialportal.cpp
100%        New File                  80        socialportal.hpp
100%        New File                1744        trade_item.cpp
100%        New File                  78        trade_item.hpp
100%        New File                1872        trash_item.cpp
100%        New File                  78        trash_item.hpp
100%        New File                1760        __dialog_return.cpp
100%        New File                 172        __dialog_return.hpp
          New Dir          2    C:\GTPS\Gurotopia\include\admin\
100%        New File               26070        admin.cpp
100%        New File                 341        admin.hpp
          New Dir          2    C:\GTPS\Gurotopia\include\automate\
100%        New File                2650        holiday.cpp
100%        New File                 418        holiday.hpp
          New Dir         26    C:\GTPS\Gurotopia\include\commands\
100%        New File                 790        find.cpp
100%        New File                  79        find.hpp
100%        New File                 265        ghost.cpp
100%        New File                  80        ghost.hpp
100%        New File                 823        me.cpp
100%        New File                  77        me.hpp
100%        New File                2037        msg.cpp
100%        New File                  78        msg.hpp
100%        New File                 174        news.cpp
100%        New File                  79        news.hpp
100%        New File                1086        punch.cpp
100%        New File                 124        punch.hpp
100%        New File                2055        sb.cpp
100%        New File                  77        sb.hpp
100%        New File                 456        skin.cpp
100%        New File                  79        skin.hpp
100%        New File                 858        time.cpp
100%        New File                 105        time.hpp
100%        New File                 696        warp.cpp
100%        New File                  79        warp.hpp
100%        New File                3072        weather.cpp
100%        New File                 125        weather.hpp
100%        New File                 791        who.cpp
100%        New File                  78        who.hpp
100%        New File                1924        __command.cpp
100%        New File                 139        __command.hpp
          New Dir         10    C:\GTPS\Gurotopia\include\database\
100%        New File                6517        database.cpp
100%        New File                4875        database.hpp
100%        New File                7348        items.cpp
100%        New File                5438        items.hpp
100%        New File               12012        peer.cpp
100%        New File                8488        peer.hpp
100%        New File                1111        shouhin.cpp
100%        New File                 428        shouhin.hpp
100%        New File               20552        world.cpp
100%        New File                5790        world.hpp
          New Dir          9    C:\GTPS\Gurotopia\include\enet\
100%        New File                 592        callbacks.h
100%        New File               28088        enet.h
100%        New File                1168        list.h
100%        New File                5906        protocol.h
100%        New File                 530        time.h
100%        New File                 347        types.h
100%        New File                1346        unix.h
100%        New File                 303        utility.h
100%        New File                1569        win32.h
          New Dir          3    C:\GTPS\Gurotopia\include\enet\lib\
100%        New File               96784        libenet.a
100%        New File               79510        libenet_32.a
100%        New File              119456        libenet_macos.a
          New Dir          8    C:\GTPS\Gurotopia\include\eventType\
100%        New File                 840        connect.cpp
100%        New File                  54        connect.hpp
100%        New File                 142        disconnect.cpp
100%        New File                  56        disconnect.hpp
100%        New File                1980        receive.cpp
100%        New File                  53        receive.hpp
100%        New File                 293        _eventType.cpp
100%        New File                  78        _eventType.hpp
          New Dir         18    C:\GTPS\Gurotopia\include\gamePacket\
100%        New File                 167        disconnect.cpp
100%        New File                  81        disconnect.hpp
100%        New File                3029        item_activate.cpp
100%        New File                  84        item_activate.hpp
100%        New File                1753        item_activate_object.cpp
100%        New File                  91        item_activate_object.hpp
100%        New File                 633        movement.cpp
100%        New File                  79        movement.hpp
100%        New File                 239        ping_reply.cpp
100%        New File                  81        ping_reply.hpp
100%        New File                 706        set_icon_state.cpp
100%        New File                  85        set_icon_state.hpp
100%        New File                2460        tile_activate.cpp
100%        New File                  84        tile_activate.hpp
100%        New File               39699        tile_change.cpp
100%        New File                  82        tile_change.hpp
100%        New File                 583        _gamePacket.cpp
100%        New File                 132        _gamePacket.hpp
          New Dir          4    C:\GTPS\Gurotopia\include\https\
100%        New File                6248        https.cpp
100%        New File                  62        https.hpp
100%        New File                1259        server_data.cpp
100%        New File                 369        server_data.hpp
          New Dir         12    C:\GTPS\Gurotopia\include\mysql\
100%        New File                4943        errmsg.h
100%        New File               19175        mariadb_com.h
100%        New File                2593        mariadb_ctype.h
100%        New File                8270        mariadb_dyncol.h
100%        New File               19328        mariadb_rpl.h
100%        New File                9931        mariadb_stmt.h
100%        New File                1273        mariadb_version.h
100%        New File                1619        ma_list.h
100%        New File                4580        ma_pvio.h
100%        New File                4970        ma_tls.h
100%        New File               42801        mysql.h
100%        New File               48260        mysqld_error.h
          New Dir          1    C:\GTPS\Gurotopia\include\mysql\lib\
100%        New File               55892        libmariadb.lib
          New Dir         29    C:\GTPS\Gurotopia\include\onVariant\
100%        New File                 639        Action.cpp
100%        New File                 102        Action.hpp
100%        New File                 461        BillboardChange.cpp
100%        New File                  82        BillboardChange.hpp
100%        New File                 222        ConsoleMessage.cpp
100%        New File                 140        ConsoleMessage.hpp
100%        New File                 416        CountryState.cpp
100%        New File                  79        CountryState.hpp
100%        New File                2051        EmoticonDataChanged.cpp
100%        New File                  86        EmoticonDataChanged.hpp
100%        New File                 979        EventButtonDataSet.cpp
100%        New File                  98        EventButtonDataSet.hpp
100%        New File                 279        NameChanged.cpp
100%        New File                  78        NameChanged.hpp
100%        New File                3367        RequestGazette.cpp
100%        New File                  81        RequestGazette.hpp
100%        New File                1659        RequestWorldSelectMenu.cpp
100%        New File                  89        RequestWorldSelectMenu.hpp
100%        New File                 805        SetBux.cpp
100%        New File                  73        SetBux.hpp
100%        New File                1570        SetClothing.cpp
100%        New File                  76        SetClothing.hpp
100%        New File                 611        Spawn.cpp
100%        New File                 191        Spawn.hpp
100%        New File                 687        TradeStatus.cpp
100%        New File                  76        TradeStatus.hpp
100%        New File                 938        WorldLockStorageResponse.cpp
100%        New File                 885        WorldLockStorageResponse.cpp.bak
100%        New File                  89        WorldLockStorageResponse.hpp
          New Dir          2    C:\GTPS\Gurotopia\include\proton\
100%        New File                2798        Variant.cpp
100%        New File                5216        Variant.hpp
          New Dir          2    C:\GTPS\Gurotopia\include\proton\Math\
100%        New File                4597        vec2.hpp
100%        New File                4838        vec3.hpp
          New Dir          2    C:\GTPS\Gurotopia\include\security\
100%        New File                4660        guest_identity.hpp
100%        New File                2332        login_session.hpp
          New Dir         13    C:\GTPS\Gurotopia\include\tools\
100%        New File                 694        conversions.cpp
100%        New File                 217        conversions.hpp
100%        New File                 208        conversions.hpp.20261112_030104.bak
100%        New File                4471        create_dialog.cpp
100%        New File                1899        create_dialog.hpp
100%        New File                 503        random.cpp
100%        New File                 124        random.hpp
100%        New File                1455        string.cpp
100%        New File                1187        string.hpp
100%        New File                 213        terminal.cpp
100%        New File                  88        terminal.hpp
100%        New File                 157        time.cpp
100%        New File                  28        time.hpp
          New Dir          1    C:\GTPS\Gurotopia\resources\
100%        New File               38957        store.txt
          New Dir          2    C:\GTPS\Gurotopia\resources\ctx\
100%        New File                1489        server.crt
100%        New File                1704        server.key
          New Dir         15    C:\GTPS\login-gurotopia\
100%        New File                  77        .env
100%        New File                  59        .env.example
100%        New File                 549        .gitignore
100%        New File                5152        apply_guest_login_v2.js
100%        New File               17321        bun.lock
100%        New File                 554        db-check.ts
100%        New File               17081        index.ts
100%        New File               16534        index.ts.2026-11-11T10-40-25-612Z.bak
100%        New File               16262        index.ts.before-debug.bak
100%        New File                1084        LICENSE
100%        New File                3819        LOGIN_API_GUEST.patch
100%        New File                 470        package.json
100%        New File                7045        README.md
100%        New File               11404        tsconfig.json
100%        New File                 191        vercel.json
          New Dir          5    C:\GTPS\login-gurotopia\.git\
100%        New File                 307        config
100%        New File                  73        description
100%        New File                  21        HEAD
100%        New File                1114        index
100%        New File                 112        packed-refs
          New Dir         14    C:\GTPS\login-gurotopia\.git\hooks\
100%        New File                 478        applypatch-msg.sample
100%        New File                1972        commit-msg.sample
100%        New File                4611        fsmonitor-watchman.sample
100%        New File                 189        post-update.sample
100%        New File                 424        pre-applypatch.sample
100%        New File                1649        pre-commit.sample
100%        New File                 416        pre-merge-commit.sample
100%        New File                1374        pre-push.sample
100%        New File                4898        pre-rebase.sample
100%        New File                 544        pre-receive.sample
100%        New File                1492        prepare-commit-msg.sample
100%        New File                2783        push-to-checkout.sample
100%        New File                2308        sendemail-validate.sample
100%        New File                3650        update.sample
          New Dir          1    C:\GTPS\login-gurotopia\.git\info\
100%        New File                 240        exclude
          New Dir          1    C:\GTPS\login-gurotopia\.git\logs\
100%        New File                 179        HEAD
          New Dir          0    C:\GTPS\login-gurotopia\.git\logs\refs\
          New Dir          1    C:\GTPS\login-gurotopia\.git\logs\refs\heads\
100%        New File                 179        main
          New Dir          0    C:\GTPS\login-gurotopia\.git\logs\refs\remotes\
          New Dir          1    C:\GTPS\login-gurotopia\.git\logs\refs\remotes\origin\
100%        New File                 179        HEAD
          New Dir          0    C:\GTPS\login-gurotopia\.git\objects\
          New Dir          0    C:\GTPS\login-gurotopia\.git\objects\info\
          New Dir          3    C:\GTPS\login-gurotopia\.git\objects\pack\
100%        New File                4264        pack-b8403694baad5fdcdd5b3556b1eb6bcc28925dcc.idx
100%        New File               69197        pack-b8403694baad5fdcdd5b3556b1eb6bcc28925dcc.pack
100%        New File                 508        pack-b8403694baad5fdcdd5b3556b1eb6bcc28925dcc.rev
          New Dir          0    C:\GTPS\login-gurotopia\.git\refs\
          New Dir          1    C:\GTPS\login-gurotopia\.git\refs\heads\
100%        New File                  41        main
          New Dir          0    C:\GTPS\login-gurotopia\.git\refs\remotes\
          New Dir          1    C:\GTPS\login-gurotopia\.git\refs\remotes\origin\
100%        New File                  30        HEAD
          New Dir          0    C:\GTPS\login-gurotopia\.git\refs\tags\
          New Dir          1    C:\GTPS\login-gurotopia\.github\
100%        New File                  58        FUNDING.yml
          New Dir          0    C:\GTPS\login-gurotopia\node_modules\
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\.bin\
100%        New File                  60        tsc.bunx
100%        New File                8192        tsc.exe
100%        New File                  70        tsserver.bunx
100%        New File                8192        tsserver.exe
          New Dir          0    C:\GTPS\login-gurotopia\node_modules\@types\
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\@types\body-parser\
100%        New File                3844        index.d.ts
100%        New File                1141        LICENSE
100%        New File                1966        package.json
100%        New File                 937        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\@types\connect\
100%        New File                3239        index.d.ts
100%        New File                1141        LICENSE
100%        New File                 965        package.json
100%        New File                 562        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\@types\cors\
100%        New File                1578        index.d.ts
100%        New File                1141        LICENSE
100%        New File                1132        package.json
100%        New File                2297        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\@types\express\
100%        New File                4189        index.d.ts
100%        New File                1141        LICENSE
100%        New File                1412        package.json
100%        New File                 834        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\@types\express-serve-static-core\
100%        New File               41491        index.d.ts
100%        New File                1141        LICENSE
100%        New File                1621        package.json
100%        New File                 928        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\@types\http-errors\
100%        New File                3946        index.d.ts
100%        New File                1141        LICENSE
100%        New File                1150        package.json
100%        New File                 590        README.md
          New Dir         53    C:\GTPS\login-gurotopia\node_modules\@types\node\
100%        New File               40074        assert.d.ts
100%        New File               26213        async_hooks.d.ts
100%        New File               22610        buffer.buffer.d.ts
100%        New File               82641        buffer.d.ts
100%        New File               63307        child_process.d.ts
100%        New File               21212        cluster.d.ts
100%        New File                6758        console.d.ts
100%        New File                 820        constants.d.ts
100%        New File              172085        crypto.d.ts
100%        New File               25654        dgram.d.ts
100%        New File               25053        diagnostics_channel.d.ts
100%        New File               36127        dns.d.ts
100%        New File                7510        domain.d.ts
100%        New File               49093        events.d.ts
100%        New File              197422        fs.d.ts
100%        New File                5132        globals.d.ts
100%        New File                4864        globals.typedarray.d.ts
100%        New File               94410        http.d.ts
100%        New File              118435        http2.d.ts
100%        New File               16683        https.d.ts
100%        New File                5031        index.d.ts
100%        New File               10394        inspector.d.ts
100%        New File              214487        inspector.generated.d.ts
100%        New File                1141        LICENSE
100%        New File               37379        module.d.ts
100%        New File               41656        net.d.ts
100%        New File               19438        os.d.ts
100%        New File                4509        package.json
100%        New File                7888        path.d.ts
100%        New File               24043        perf_hooks.d.ts
100%        New File              104954        process.d.ts
100%        New File                5458        punycode.d.ts
100%        New File                7130        querystring.d.ts
100%        New File               29946        quic.d.ts
100%        New File               22339        readline.d.ts
100%        New File                1582        README.md
100%        New File               18464        repl.d.ts
100%        New File                6638        sea.d.ts
100%        New File               45380        sqlite.d.ts
100%        New File               87891        stream.d.ts
100%        New File                2814        string_decoder.d.ts
100%        New File              102989        test.d.ts
100%        New File                7948        timers.d.ts
100%        New File               57695        tls.d.ts
100%        New File                8931        trace_events.d.ts
100%        New File               12238        tty.d.ts
100%        New File               23513        url.d.ts
100%        New File               64615        util.d.ts
100%        New File               40441        v8.d.ts
100%        New File               52901        vm.d.ts
100%        New File                9125        wasi.d.ts
100%        New File               31300        worker_threads.d.ts
100%        New File               23906        zlib.d.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\@types\node\assert\
100%        New File                2828        strict.d.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\@types\node\compatibility\
100%        New File                1303        iterators.d.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\@types\node\dns\
100%        New File               21112        promises.d.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\@types\node\fs\
100%        New File               56860        promises.d.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\@types\node\inspector\
100%        New File                1681        promises.d.ts
          New Dir          2    C:\GTPS\login-gurotopia\node_modules\@types\node\path\
100%        New File                 194        posix.d.ts
100%        New File                 194        win32.d.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\@types\node\readline\
100%        New File                6444        promises.d.ts
          New Dir          3    C:\GTPS\login-gurotopia\node_modules\@types\node\stream\
100%        New File                1572        consumers.d.ts
100%        New File                7347        promises.d.ts
100%        New File               11991        web.d.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\@types\node\test\
100%        New File                4046        reporters.d.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\@types\node\timers\
100%        New File                3785        promises.d.ts
          New Dir          3    C:\GTPS\login-gurotopia\node_modules\@types\node\ts5.6\
100%        New File               21861        buffer.buffer.d.ts
100%        New File                1238        globals.typedarray.d.ts
100%        New File                5362        index.d.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\@types\node\ts5.6\compatibility\
100%        New File                3811        float16array.d.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\@types\node\ts5.7\
100%        New File                5349        index.d.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\@types\node\ts5.7\compatibility\
100%        New File                3872        float16array.d.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\@types\node\util\
100%        New File               23832        types.d.ts
          New Dir         16    C:\GTPS\login-gurotopia\node_modules\@types\node\web-globals\
100%        New File                1989        abortcontroller.d.ts
100%        New File                 902        blob.d.ts
100%        New File                 149        console.d.ts
100%        New File                1449        crypto.d.ts
100%        New File                2565        domexception.d.ts
100%        New File                 414        encoding.d.ts
100%        New File                3367        events.d.ts
100%        New File                2741        fetch.d.ts
100%        New File                 259        importmeta.d.ts
100%        New File                1113        messaging.d.ts
100%        New File                 891        navigator.d.ts
100%        New File                2551        performance.d.ts
100%        New File                 724        storage.d.ts
100%        New File                6707        streams.d.ts
100%        New File                1557        timers.d.ts
100%        New File                 800        url.d.ts
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\@types\qs\
100%        New File                3591        index.d.ts
100%        New File                1141        LICENSE
100%        New File                1974        package.json
100%        New File                 803        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\@types\range-parser\
100%        New File                1029        index.d.ts
100%        New File                1141        LICENSE
100%        New File                 805        package.json
100%        New File                1640        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\@types\send\
100%        New File                6078        index.d.ts
100%        New File                1141        LICENSE
100%        New File                1167        package.json
100%        New File                 620        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\@types\serve-static\
100%        New File                5392        index.d.ts
100%        New File                1141        LICENSE
100%        New File                1367        package.json
100%        New File                 760        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\accepts\
100%        New File                5218        HISTORY.md
100%        New File                5253        index.js
100%        New File                1167        LICENSE
100%        New File                1157        package.json
100%        New File                4122        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\body-parser\
100%        New File                1312        index.js
100%        New File                1172        LICENSE
100%        New File                1359        package.json
100%        New File               19560        README.md
          New Dir          2    C:\GTPS\login-gurotopia\node_modules\body-parser\lib\
100%        New File                5401        read.js
100%        New File                2031        utils.js
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\body-parser\lib\types\
100%        New File                3573        json.js
100%        New File                 799        raw.js
100%        New File                 663        text.js
100%        New File                3611        urlencoded.js
          New Dir         26    C:\GTPS\login-gurotopia\node_modules\bun-types\
100%        New File              221516        bun.d.ts
100%        New File                  87        bun.ns.d.ts
100%        New File                1916        bundle.d.ts
100%        New File                2501        CLAUDE.md
100%        New File                6183        deprecated.d.ts
100%        New File                6532        devserver.d.ts
100%        New File                 538        extensions.d.ts
100%        New File                2860        fetch.d.ts
100%        New File               33370        ffi.d.ts
100%        New File               66520        globals.d.ts
100%        New File                6875        html-rewriter.d.ts
100%        New File                1306        index.d.ts
100%        New File                8512        jsc.d.ts
100%        New File               10666        overrides.d.ts
100%        New File                 807        package.json
100%        New File                 973        README.md
100%        New File              135018        redis.d.ts
100%        New File               44167        s3.d.ts
100%        New File                3181        security.d.ts
100%        New File               38298        serve.d.ts
100%        New File               10491        shell.d.ts
100%        New File               27885        sql.d.ts
100%        New File               38168        sqlite.d.ts
100%        New File                 976        test-globals.d.ts
100%        New File               76145        test.d.ts
100%        New File                7810        wasm.d.ts
          New Dir          6    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\
100%        New File                3038        feedback.mdx
100%        New File                6333        index.mdx
100%        New File                9756        installation.mdx
100%        New File                6148        quickstart.mdx
100%        New File                 645        README.md
100%        New File                1644        typescript.mdx
          New Dir         12    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\bundler\
100%        New File               18330        bytecode.mdx
100%        New File               30926        css.mdx
100%        New File               67262        esbuild.mdx
100%        New File               37007        executables.mdx
100%        New File               26528        fullstack.mdx
100%        New File               10083        hot-reloading.mdx
100%        New File               13141        html-static.mdx
100%        New File               52771        index.mdx
100%        New File               11488        loaders.mdx
100%        New File               10853        macros.mdx
100%        New File               18329        minifier.mdx
100%        New File               13109        plugins.mdx
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\
100%        New File                 218        index.mdx
          New Dir         22    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\binary\
100%        New File                1106        arraybuffer-to-array.mdx
100%        New File                 745        arraybuffer-to-blob.mdx
100%        New File                 824        arraybuffer-to-buffer.mdx
100%        New File                 524        arraybuffer-to-string.mdx
100%        New File                1012        arraybuffer-to-typedarray.mdx
100%        New File                 507        blob-to-arraybuffer.mdx
100%        New File                 583        blob-to-dataview.mdx
100%        New File                 545        blob-to-stream.mdx
100%        New File                 502        blob-to-string.mdx
100%        New File                 591        blob-to-typedarray.mdx
100%        New File                 504        buffer-to-arraybuffer.mdx
100%        New File                 507        buffer-to-blob.mdx
100%        New File                1404        buffer-to-readablestream.mdx
100%        New File                 621        buffer-to-string.mdx
100%        New File                 598        buffer-to-typedarray.mdx
100%        New File                 603        dataview-to-string.mdx
100%        New File                 983        typedarray-to-arraybuffer.mdx
100%        New File                 591        typedarray-to-blob.mdx
100%        New File                 589        typedarray-to-buffer.mdx
100%        New File                 665        typedarray-to-dataview.mdx
100%        New File                1496        typedarray-to-readablestream.mdx
100%        New File                 572        typedarray-to-string.mdx
          New Dir          6    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\deployment\
100%        New File                7889        aws-lambda.mdx
100%        New File                6402        digital-ocean.mdx
100%        New File                6512        google-cloud-run.mdx
100%        New File                4439        railway.mdx
100%        New File                2351        render.mdx
100%        New File                2989        vercel.mdx
          New Dir         28    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\ecosystem\
100%        New File                2094        astro.mdx
100%        New File                2261        discordjs.mdx
100%        New File                6114        docker.mdx
100%        New File                4157        drizzle.mdx
100%        New File                1048        elysia.mdx
100%        New File                 960        express.mdx
100%        New File                6817        gel.mdx
100%        New File                 974        hono.mdx
100%        New File                2109        mongoose.mdx
100%        New File                5990        neon-drizzle.mdx
100%        New File                1998        neon-serverless-postgres.mdx
100%        New File                3295        nextjs.mdx
100%        New File                2629        nuxt.mdx
100%        New File                1702        pm2.mdx
100%        New File                5243        prisma-postgres.mdx
100%        New File                5400        prisma.mdx
100%        New File                3981        qwik.mdx
100%        New File                1591        react.mdx
100%        New File                2216        remix.mdx
100%        New File                1656        sentry.mdx
100%        New File                1449        solidstart.mdx
100%        New File                1474        ssr-react.mdx
100%        New File                1388        stric.mdx
100%        New File                4420        sveltekit.mdx
100%        New File                3775        systemd.mdx
100%        New File               28783        tanstack-start.mdx
100%        New File                2795        upstash.mdx
100%        New File                1676        vite.mdx
          New Dir          2    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\html-rewriter\
100%        New File                2231        extract-links.mdx
100%        New File                3141        extract-social-meta.mdx
          New Dir         12    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\http\
100%        New File                1893        cluster.mdx
100%        New File                1185        fetch-unix.mdx
100%        New File                 734        fetch.mdx
100%        New File                3106        file-uploads.mdx
100%        New File                 745        hot.mdx
100%        New File                1745        proxy.mdx
100%        New File                1460        server.mdx
100%        New File                 511        simple.mdx
100%        New File                1405        stream-file.mdx
100%        New File                1251        stream-iterator.mdx
100%        New File                 735        stream-node-streams-in-bun.mdx
100%        New File                 979        tls.mdx
          New Dir         17    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\install\
100%        New File                 514        add-dev.mdx
100%        New File                 894        add-git.mdx
100%        New File                 532        add-optional.mdx
100%        New File                 886        add-peer.mdx
100%        New File                 818        add-tarball.mdx
100%        New File                 936        add.mdx
100%        New File                2877        azure-artifacts.mdx
100%        New File                1001        cicd.mdx
100%        New File                1025        custom-registry.mdx
100%        New File                9546        from-npm-install-to-bun-install.mdx
100%        New File                1424        git-diff-bun-lockfile.mdx
100%        New File                1011        jfrog-artifactory.mdx
100%        New File                 485        npm-alias.mdx
100%        New File                1361        registry-scope.mdx
100%        New File                1872        trusted.mdx
100%        New File                2200        workspaces.mdx
100%        New File                1356        yarnlock.mdx
          New Dir          9    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\process\
100%        New File                1123        argv.mdx
100%        New File                 516        ctrl-c.mdx
100%        New File                2301        ipc.mdx
100%        New File                 302        nanoseconds.mdx
100%        New File                 730        os-signals.mdx
100%        New File                 738        spawn-stderr.mdx
100%        New File                 638        spawn-stdout.mdx
100%        New File                 817        spawn.mdx
100%        New File                1426        stdin.mdx
          New Dir          9    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\read-file\
100%        New File                 944        arraybuffer.mdx
100%        New File                 788        buffer.mdx
100%        New File                 484        exists.mdx
100%        New File                 619        json.mdx
100%        New File                 560        mime.mdx
100%        New File                 864        stream.mdx
100%        New File                 617        string.mdx
100%        New File                 736        uint8array.mdx
100%        New File                1782        watch.mdx
          New Dir         19    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\runtime\
100%        New File                7736        build-time-constants.mdx
100%        New File                1066        cicd.mdx
100%        New File                2079        codesign-macos-executable.mdx
100%        New File                4309        define-constant.mdx
100%        New File                1018        delete-directory.mdx
100%        New File                 424        delete-file.mdx
100%        New File                 875        heap-snapshot.mdx
100%        New File                 475        import-html.mdx
100%        New File                 977        import-json.mdx
100%        New File                 583        import-toml.mdx
100%        New File                2012        import-yaml.mdx
100%        New File                 825        read-env.mdx
100%        New File                1055        set-env.mdx
100%        New File                1007        shell.mdx
100%        New File                1076        timezone.mdx
100%        New File                 805        tsconfig-paths.mdx
100%        New File                1329        typescript.mdx
100%        New File                2252        vscode-debugger.mdx
100%        New File                4137        web-debugger.mdx
          New Dir         12    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\streams\
100%        New File                 467        node-readable-to-arraybuffer.mdx
100%        New File                 673        node-readable-to-blob.mdx
100%        New File                 623        node-readable-to-json.mdx
100%        New File                 610        node-readable-to-string.mdx
100%        New File                 451        node-readable-to-uint8array.mdx
100%        New File                 642        to-array.mdx
100%        New File                 545        to-arraybuffer.mdx
100%        New File                 524        to-blob.mdx
100%        New File                 826        to-buffer.mdx
100%        New File                 503        to-json.mdx
100%        New File                 527        to-string.mdx
100%        New File                1083        to-typedarray.mdx
          New Dir         19    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\test\
100%        New File                 561        bail.mdx
100%        New File                4695        concurrent-test-glob.mdx
100%        New File                1624        coverage-threshold.mdx
100%        New File                1462        coverage.mdx
100%        New File                1962        happy-dom.mdx
100%        New File                3831        migrate-from-jest.mdx
100%        New File                1298        mock-clock.mdx
100%        New File                1741        mock-functions.mdx
100%        New File                 434        rerun-each.mdx
100%        New File                2333        run-tests.mdx
100%        New File                 788        skip-tests.mdx
100%        New File                2210        snapshot.mdx
100%        New File                1109        spy-on.mdx
100%        New File                2892        svelte-test.mdx
100%        New File                3266        testing-library.mdx
100%        New File                 441        timeout.mdx
100%        New File                1569        todo-tests.mdx
100%        New File                1066        update-snapshots.mdx
100%        New File                 604        watch-mode.mdx
          New Dir         19    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\util\
100%        New File                 616        base64.mdx
100%        New File                1132        deep-equals.mdx
100%        New File                 441        deflate.mdx
100%        New File                 860        detect-bun.mdx
100%        New File                 620        entrypoint.mdx
100%        New File                 643        escape-html.mdx
100%        New File                 336        file-url-to-path.mdx
100%        New File                 414        gzip.mdx
100%        New File                1534        hash-a-password.mdx
100%        New File                 415        import-meta-dir.mdx
100%        New File                 482        import-meta-file.mdx
100%        New File                 500        import-meta-path.mdx
100%        New File                 586        javascript-uuid.mdx
100%        New File                 675        main.mdx
100%        New File                 336        path-to-file-url.mdx
100%        New File                 591        sleep.mdx
100%        New File                2180        upgrade.mdx
100%        New File                 535        version.mdx
100%        New File                 499        which-path-to-executable-bin.mdx
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\websocket\
100%        New File                 769        compression.mdx
100%        New File                2069        context.mdx
100%        New File                1440        pubsub.mdx
100%        New File                1019        simple.mdx
          New Dir         10    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\guides\write-file\
100%        New File                1184        append.mdx
100%        New File                1131        basic.mdx
100%        New File                 854        blob.mdx
100%        New File                 603        cat.mdx
100%        New File                 623        file-cp.mdx
100%        New File                1301        filesink.mdx
100%        New File                 720        response.mdx
100%        New File                 620        stdout.mdx
100%        New File                 565        stream.mdx
100%        New File                 411        unlink.mdx
          New Dir         12    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\pm\
100%        New File                2731        bunx.mdx
100%        New File                7163        catalogs.mdx
100%        New File                4132        filter.mdx
100%        New File                3926        global-cache.mdx
100%        New File                8630        isolated-installs.mdx
100%        New File                2767        lifecycle.mdx
100%        New File                1785        lockfile.mdx
100%        New File                3129        npmrc.mdx
100%        New File                2463        overrides.mdx
100%        New File                1052        scopes-registries.mdx
100%        New File                2637        security-scanner-api.mdx
100%        New File                4608        workspaces.mdx
          New Dir         12    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\pm\cli\
100%        New File                4503        add.mdx
100%        New File                1801        audit.mdx
100%        New File                1342        info.mdx
100%        New File               21743        install.mdx
100%        New File                1394        link.mdx
100%        New File               11808        outdated.mdx
100%        New File                2787        patch.mdx
100%        New File                7310        pm.mdx
100%        New File                3934        publish.mdx
100%        New File                 219        remove.mdx
100%        New File                4119        update.mdx
100%        New File                1907        why.mdx
          New Dir          7    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\project\
100%        New File                8093        benchmarking.mdx
100%        New File                6633        bindgen.mdx
100%        New File                4429        building-windows.mdx
100%        New File               16982        contributing.mdx
100%        New File                 511        feedback.mdx
100%        New File                8208        license.mdx
100%        New File                 469        roadmap.mdx
          New Dir         40    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\runtime\
100%        New File                4659        auto-install.mdx
100%        New File               30560        binary-data.mdx
100%        New File               14783        bun-apis.mdx
100%        New File               21465        bunfig.mdx
100%        New File                4930        c-compiler.mdx
100%        New File               20791        child-process.mdx
100%        New File               10333        color.mdx
100%        New File                1586        console.mdx
100%        New File               11964        cookies.mdx
100%        New File               14190        debugger.mdx
100%        New File               12873        environment-variables.mdx
100%        New File               15340        ffi.mdx
100%        New File                8493        file-io.mdx
100%        New File                2732        file-system-router.mdx
100%        New File               11830        file-types.mdx
100%        New File                4058        glob.mdx
100%        New File               24886        globals.mdx
100%        New File                9772        hashing.mdx
100%        New File               10247        html-rewriter.mdx
100%        New File                7290        index.mdx
100%        New File               10022        jsx.mdx
100%        New File               18628        module-resolution.mdx
100%        New File                 643        node-api.mdx
100%        New File               15844        nodejs-compat.mdx
100%        New File               13112        plugins.mdx
100%        New File               15526        redis.mdx
100%        New File               28469        s3.mdx
100%        New File                8675        secrets.mdx
100%        New File                2023        semver.mdx
100%        New File               15709        shell.mdx
100%        New File               51858        sql.mdx
100%        New File               24115        sqlite.mdx
100%        New File                6469        streams.mdx
100%        New File                7266        transpiler.mdx
100%        New File                1606        typescript.mdx
100%        New File               30194        utils.mdx
100%        New File                6071        watch-mode.mdx
100%        New File               11003        web-apis.mdx
100%        New File               11263        workers.mdx
100%        New File               10216        yaml.mdx
          New Dir          7    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\runtime\http\
100%        New File                2076        cookies.mdx
100%        New File                1041        error-handling.mdx
100%        New File                 737        metrics.mdx
100%        New File                9232        routing.mdx
100%        New File               15821        server.mdx
100%        New File                2410        tls.mdx
100%        New File               13564        websockets.mdx
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\runtime\networking\
100%        New File                3882        dns.mdx
100%        New File               14927        fetch.mdx
100%        New File                5652        tcp.mdx
100%        New File                3747        udp.mdx
          New Dir          2    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\runtime\templating\
100%        New File               11000        create.mdx
100%        New File                1813        init.mdx
          New Dir          0    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\snippets\
          New Dir         14    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\snippets\cli\
100%        New File                4787        add.mdx
100%        New File                5938        build.mdx
100%        New File                1305        bunx.mdx
100%        New File                 361        feedback.mdx
100%        New File                1921        init.mdx
100%        New File                4379        install.mdx
100%        New File                4588        link.mdx
100%        New File                3883        outdated.mdx
100%        New File                4851        patch.mdx
100%        New File                5357        publish.mdx
100%        New File                4002        remove.mdx
100%        New File                9320        run.mdx
100%        New File                2627        test.mdx
100%        New File                4035        update.mdx
          New Dir         12    C:\GTPS\login-gurotopia\node_modules\bun-types\docs\test\
100%        New File               11836        code-coverage.mdx
100%        New File               12470        configuration.mdx
100%        New File                4028        dates-times.mdx
100%        New File                3007        discovery.mdx
100%        New File                6466        dom.mdx
100%        New File               11385        index.mdx
100%        New File                8789        lifecycle.mdx
100%        New File               18574        mocks.mdx
100%        New File                4735        reporters.mdx
100%        New File                8355        runtime-behavior.mdx
100%        New File               10555        snapshots.mdx
100%        New File               18749        writing-tests.mdx
          New Dir          0    C:\GTPS\login-gurotopia\node_modules\bun-types\vendor\
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\bun-types\vendor\expect-type\
100%        New File               13929        branding.d.ts
100%        New File               44689        index.d.ts
100%        New File               16053        messages.d.ts
100%        New File               29089        overloads.d.ts
100%        New File               18656        utils.d.ts
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\bytes\
100%        New File                1775        History.md
100%        New File                3613        index.js
100%        New File                1153        LICENSE
100%        New File                 959        package.json
100%        New File                4770        Readme.md
          New Dir         19    C:\GTPS\login-gurotopia\node_modules\call-bind-apply-helpers\
100%        New File                 232        .eslintrc
100%        New File                 139        .nycrc
100%        New File                  23        actualApply.d.ts
100%        New File                 280        actualApply.js
100%        New File                 614        applyBind.d.ts
100%        New File                 264        applyBind.js
100%        New File                1938        CHANGELOG.md
100%        New File                  34        functionApply.d.ts
100%        New File                  99        functionApply.js
100%        New File                  33        functionCall.d.ts
100%        New File                  97        functionCall.js
100%        New File                2226        index.d.ts
100%        New File                 511        index.js
100%        New File                1071        LICENSE
100%        New File                2480        package.json
100%        New File                2330        README.md
100%        New File                  82        reflectApply.d.ts
100%        New File                 132        reflectApply.js
100%        New File                 115        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\call-bind-apply-helpers\.github\
100%        New File                 594        FUNDING.yml
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\call-bind-apply-helpers\test\
100%        New File                2658        index.js
          New Dir          9    C:\GTPS\login-gurotopia\node_modules\call-bound\
100%        New File                 138        .eslintrc
100%        New File                 139        .nycrc
100%        New File                2880        CHANGELOG.md
100%        New File                4651        index.d.ts
100%        New File                 687        index.js
100%        New File                1071        LICENSE
100%        New File                2507        package.json
100%        New File                1897        README.md
100%        New File                 137        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\call-bound\.github\
100%        New File                 581        FUNDING.yml
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\call-bound\test\
100%        New File                2418        index.js
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\content-disposition\
100%        New File                1265        HISTORY.md
100%        New File               10551        index.js
100%        New File                1094        LICENSE
100%        New File                1082        package.json
100%        New File                5223        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\content-type\
100%        New File                 523        HISTORY.md
100%        New File                5002        index.js
100%        New File                1089        LICENSE
100%        New File                1075        package.json
100%        New File                2782        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\cookie\
100%        New File                8166        index.js
100%        New File                1175        LICENSE
100%        New File                1092        package.json
100%        New File               11769        README.md
100%        New File                1180        SECURITY.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\cookie-signature\
100%        New File                1481        History.md
100%        New File                1413        index.js
100%        New File                1124        LICENSE
100%        New File                 548        package.json
100%        New File                 427        Readme.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\cors\
100%        New File                1028        CONTRIBUTING.md
100%        New File                1169        HISTORY.md
100%        New File                1095        LICENSE
100%        New File                 867        package.json
100%        New File                9206        README.md
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\cors\lib\
100%        New File                6623        index.js
          New Dir          3    C:\GTPS\login-gurotopia\node_modules\debug\
100%        New File                1139        LICENSE
100%        New File                1479        package.json
100%        New File               22115        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\debug\src\
100%        New File                6103        browser.js
100%        New File                6915        common.js
100%        New File                 314        index.js
100%        New File                4728        node.js
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\depd\
100%        New File                2256        History.md
100%        New File               10932        index.js
100%        New File                1094        LICENSE
100%        New File                1335        package.json
100%        New File                9988        Readme.md
          New Dir          0    C:\GTPS\login-gurotopia\node_modules\depd\lib\
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\depd\lib\browser\
100%        New File                1512        index.js
          New Dir         11    C:\GTPS\login-gurotopia\node_modules\dunder-proto\
100%        New File                  43        .eslintrc
100%        New File                 216        .nycrc
100%        New File                1547        CHANGELOG.md
100%        New File                 121        get.d.ts
100%        New File                 980        get.js
100%        New File                1073        LICENSE
100%        New File                2108        package.json
100%        New File                1907        README.md
100%        New File                 144        set.d.ts
100%        New File                1276        set.js
100%        New File                 116        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\dunder-proto\.github\
100%        New File                 583        FUNDING.yml
          New Dir          3    C:\GTPS\login-gurotopia\node_modules\dunder-proto\test\
100%        New File                1143        get.js
100%        New File                  51        index.js
100%        New File                1695        set.js
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\ee-first\
100%        New File                1684        index.js
100%        New File                1099        LICENSE
100%        New File                 859        package.json
100%        New File                2617        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\encodeurl\
100%        New File                1578        index.js
100%        New File                1089        LICENSE
100%        New File                1092        package.json
100%        New File                3221        README.md
          New Dir          9    C:\GTPS\login-gurotopia\node_modules\es-define-property\
100%        New File                 144        .eslintrc
100%        New File                 139        .nycrc
100%        New File                2296        CHANGELOG.md
100%        New File                  93        index.d.ts
100%        New File                 288        index.js
100%        New File                1071        LICENSE
100%        New File                2129        package.json
100%        New File                2056        README.md
100%        New File                 138        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\es-define-property\.github\
100%        New File                 564        FUNDING.yml
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\es-define-property\test\
100%        New File                1299        index.js
          New Dir         20    C:\GTPS\login-gurotopia\node_modules\es-errors\
100%        New File                  43        .eslintrc
100%        New File                1833        CHANGELOG.md
100%        New File                  68        eval.d.ts
100%        New File                  75        eval.js
100%        New File                  56        index.d.ts
100%        New File                  66        index.js
100%        New File                1071        LICENSE
100%        New File                2174        package.json
100%        New File                  71        range.d.ts
100%        New File                  77        range.js
100%        New File                2114        README.md
100%        New File                  83        ref.d.ts
100%        New File                  79        ref.js
100%        New File                  74        syntax.d.ts
100%        New File                  79        syntax.js
100%        New File                3170        tsconfig.json
100%        New File                  67        type.d.ts
100%        New File                  75        type.js
100%        New File                  65        uri.d.ts
100%        New File                  73        uri.js
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\es-errors\.github\
100%        New File                 555        FUNDING.yml
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\es-errors\test\
100%        New File                 356        index.js
          New Dir         14    C:\GTPS\login-gurotopia\node_modules\es-object-atoms\
100%        New File                 229        .eslintrc
100%        New File                2136        CHANGELOG.md
100%        New File                  59        index.d.ts
100%        New File                  67        index.js
100%        New File                  72        isObject.d.ts
100%        New File                 161        isObject.js
100%        New File                1071        LICENSE
100%        New File                2273        package.json
100%        New File                2603        README.md
100%        New File                 123        RequireObjectCoercible.d.ts
100%        New File                 313        RequireObjectCoercible.js
100%        New File                 352        ToObject.d.ts
100%        New File                 250        ToObject.js
100%        New File                  81        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\es-object-atoms\.github\
100%        New File                 555        FUNDING.yml
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\es-object-atoms\test\
100%        New File                1097        index.js
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\escape-html\
100%        New File                1362        index.js
100%        New File                1157        LICENSE
100%        New File                 434        package.json
100%        New File                 707        Readme.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\etag\
100%        New File                1732        HISTORY.md
100%        New File                2479        index.js
100%        New File                1094        LICENSE
100%        New File                1306        package.json
100%        New File                4198        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\express\
100%        New File                 224        index.js
100%        New File                1249        LICENSE
100%        New File                2731        package.json
100%        New File                9952        Readme.md
          New Dir          6    C:\GTPS\login-gurotopia\node_modules\express\lib\
100%        New File               13971        application.js
100%        New File                1636        express.js
100%        New File               11688        request.js
100%        New File               24876        response.js
100%        New File                5293        utils.js
100%        New File                3809        view.js
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\express-rate-limit\
100%        New File                1082        license.md
100%        New File                3173        package.json
100%        New File                9011        readme.md
100%        New File                 150        tsconfig.json
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\express-rate-limit\dist\
100%        New File               33694        index.cjs
100%        New File               20503        index.d.cts
100%        New File               20503        index.d.mts
100%        New File               20503        index.d.ts
100%        New File               32374        index.mjs
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\finalhandler\
100%        New File                5469        HISTORY.md
100%        New File                5818        index.js
100%        New File                1119        LICENSE
100%        New File                1287        package.json
100%        New File                4418        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\forwarded\
100%        New File                 400        HISTORY.md
100%        New File                1578        index.js
100%        New File                1094        LICENSE
100%        New File                1150        package.json
100%        New File                1654        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\fresh\
100%        New File                1844        HISTORY.md
100%        New File                2705        index.js
100%        New File                1174        LICENSE
100%        New File                1218        package.json
100%        New File                3348        README.md
          New Dir          8    C:\GTPS\login-gurotopia\node_modules\function-bind\
100%        New File                 253        .eslintrc
100%        New File                 216        .nycrc
100%        New File               13812        CHANGELOG.md
100%        New File                2043        implementation.js
100%        New File                 126        index.js
100%        New File                1052        LICENSE
100%        New File                2262        package.json
100%        New File                1755        README.md
          New Dir          2    C:\GTPS\login-gurotopia\node_modules\function-bind\.github\
100%        New File                 584        FUNDING.yml
100%        New File                 157        SECURITY.md
          New Dir          2    C:\GTPS\login-gurotopia\node_modules\function-bind\test\
100%        New File                 176        .eslintrc
100%        New File                8991        index.js
          New Dir          7    C:\GTPS\login-gurotopia\node_modules\get-intrinsic\
100%        New File                 647        .eslintrc
100%        New File                 139        .nycrc
100%        New File               15537        CHANGELOG.md
100%        New File               14439        index.js
100%        New File                1071        LICENSE
100%        New File                2576        package.json
100%        New File                2791        README.md
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\get-intrinsic\.github\
100%        New File                 584        FUNDING.yml
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\get-intrinsic\test\
100%        New File                8758        GetIntrinsic.js
          New Dir         13    C:\GTPS\login-gurotopia\node_modules\get-proto\
100%        New File                 104        .eslintrc
100%        New File                 139        .nycrc
100%        New File                1054        CHANGELOG.md
100%        New File                 126        index.d.ts
100%        New File                 821        index.js
100%        New File                1071        LICENSE
100%        New File                 125        Object.getPrototypeOf.d.ts
100%        New File                 156        Object.getPrototypeOf.js
100%        New File                2176        package.json
100%        New File                1794        README.md
100%        New File                  67        Reflect.getPrototypeOf.d.ts
100%        New File                 150        Reflect.getPrototypeOf.js
100%        New File                 118        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\get-proto\.github\
100%        New File                 580        FUNDING.yml
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\get-proto\test\
100%        New File                2359        index.js
          New Dir         10    C:\GTPS\login-gurotopia\node_modules\gopd\
100%        New File                 224        .eslintrc
100%        New File                3077        CHANGELOG.md
100%        New File                  42        gOPD.d.ts
100%        New File                  97        gOPD.js
100%        New File                 173        index.d.ts
100%        New File                 206        index.js
100%        New File                1071        LICENSE
100%        New File                2070        package.json
100%        New File                1562        README.md
100%        New File                 116        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\gopd\.github\
100%        New File                 575        FUNDING.yml
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\gopd\test\
100%        New File                 656        index.js
          New Dir         11    C:\GTPS\login-gurotopia\node_modules\has-symbols\
100%        New File                 164        .eslintrc
100%        New File                 139        .nycrc
100%        New File                9431        CHANGELOG.md
100%        New File                  73        index.d.ts
100%        New File                 447        index.js
100%        New File                1071        LICENSE
100%        New File                2974        package.json
100%        New File                2044        README.md
100%        New File                  69        shams.d.ts
100%        New File                1922        shams.js
100%        New File                 143        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\has-symbols\.github\
100%        New File                 582        FUNDING.yml
          New Dir          2    C:\GTPS\login-gurotopia\node_modules\has-symbols\test\
100%        New File                 654        index.js
100%        New File                2139        tests.js
          New Dir          2    C:\GTPS\login-gurotopia\node_modules\has-symbols\test\shams\
100%        New File                 797        core-js.js
100%        New File                 760        get-own-property-symbols.js
          New Dir          9    C:\GTPS\login-gurotopia\node_modules\hasown\
100%        New File                  43        .eslintrc
100%        New File                 216        .nycrc
100%        New File                2579        CHANGELOG.md
100%        New File                 117        index.d.ts
100%        New File                 206        index.js
100%        New File                1083        LICENSE
100%        New File                2283        package.json
100%        New File                1613        README.md
100%        New File                  73        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\hasown\.github\
100%        New File                 552        FUNDING.yml
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\http-errors\
100%        New File                4094        HISTORY.md
100%        New File                6430        index.js
100%        New File                1168        LICENSE
100%        New File                1410        package.json
100%        New File                5962        README.md
          New Dir          3    C:\GTPS\login-gurotopia\node_modules\iconv-lite\
100%        New File                1064        LICENSE
100%        New File                2260        package.json
100%        New File                6587        README.md
          New Dir         10    C:\GTPS\login-gurotopia\node_modules\iconv-lite\encodings\
100%        New File               20464        dbcs-codec.js
100%        New File                8881        dbcs-data.js
100%        New File                 670        index.js
100%        New File                6560        internal.js
100%        New File                2114        sbcs-codec.js
100%        New File               32034        sbcs-data-generated.js
100%        New File                4527        sbcs-data.js
100%        New File                5097        utf16.js
100%        New File                9063        utf32.js
100%        New File                8580        utf7.js
          New Dir          8    C:\GTPS\login-gurotopia\node_modules\iconv-lite\encodings\tables\
100%        New File               17717        big5-added.json
100%        New File               47320        cp936.json
100%        New File               38122        cp949.json
100%        New File               42356        cp950.json
100%        New File               41064        eucjp.json
100%        New File                2216        gb18030-ranges.json
100%        New File                1247        gbk-added.json
100%        New File               23782        shiftjis.json
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\iconv-lite\lib\
100%        New File                1035        bom-handling.js
100%        New File                4763        index.d.ts
100%        New File                6711        index.js
100%        New File                2979        streams.js
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\iconv-lite\lib\helpers\
100%        New File                 310        merge-exports.js
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\iconv-lite\types\
100%        New File                6112        encodings.d.ts
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\inherits\
100%        New File                 250        inherits.js
100%        New File                 753        inherits_browser.js
100%        New File                 749        LICENSE
100%        New File                 581        package.json
100%        New File                1625        README.md
          New Dir          3    C:\GTPS\login-gurotopia\node_modules\ip-address\
100%        New File                1061        LICENSE
100%        New File                1898        package.json
100%        New File                4755        README.md
          New Dir         20    C:\GTPS\login-gurotopia\node_modules\ip-address\dist\
100%        New File                 179        address-error.d.ts
100%        New File                 228        address-error.d.ts.map
100%        New File                 372        address-error.js
100%        New File                 301        address-error.js.map
100%        New File                 737        common.d.ts
100%        New File                 568        common.d.ts.map
100%        New File                1446        common.js
100%        New File                1259        common.js.map
100%        New File                 258        ip-address.d.ts
100%        New File                 305        ip-address.d.ts.map
100%        New File                1772        ip-address.js
100%        New File                 295        ip-address.js.map
100%        New File                5348        ipv4.d.ts
100%        New File                1538        ipv4.d.ts.map
100%        New File               10237        ipv4.js
100%        New File                5734        ipv4.js.map
100%        New File               12118        ipv6.d.ts
100%        New File                3565        ipv6.d.ts.map
100%        New File               34068        ipv6.js
100%        New File               23384        ipv6.js.map
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\ip-address\dist\v4\
100%        New File                 192        constants.d.ts
100%        New File                 243        constants.d.ts.map
100%        New File                 468        constants.js
100%        New File                 244        constants.js.map
          New Dir         12    C:\GTPS\login-gurotopia\node_modules\ip-address\dist\v6\
100%        New File                1068        constants.d.ts
100%        New File                 626        constants.d.ts.map
100%        New File                2598        constants.js
100%        New File                1189        constants.js.map
100%        New File                 629        helpers.d.ts
100%        New File                 417        helpers.d.ts.map
100%        New File                1441        helpers.js
100%        New File                1216        helpers.js.map
100%        New File                 428        regular-expressions.d.ts
100%        New File                 445        regular-expressions.d.ts.map
100%        New File                3719        regular-expressions.js
100%        New File                2600        regular-expressions.js.map
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\ip-address\src\
100%        New File                 222        address-error.ts
100%        New File                1381        common.ts
100%        New File                 192        ip-address.ts
100%        New File                8604        ipv4.ts
100%        New File               30853        ipv6.ts
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\ip-address\src\v4\
100%        New File                 290        constants.ts
          New Dir          3    C:\GTPS\login-gurotopia\node_modules\ip-address\src\v6\
100%        New File                2355        constants.ts
100%        New File                1284        helpers.ts
100%        New File                2390        regular-expressions.ts
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\ipaddr.js\
100%        New File                9738        ipaddr.min.js
100%        New File                1087        LICENSE
100%        New File                 719        package.json
100%        New File                8309        README.md
          New Dir          2    C:\GTPS\login-gurotopia\node_modules\ipaddr.js\lib\
100%        New File               19333        ipaddr.js
100%        New File                2959        ipaddr.js.d.ts
          New Dir          6    C:\GTPS\login-gurotopia\node_modules\is-promise\
100%        New File                 108        index.d.ts
100%        New File                 201        index.js
100%        New File                 151        index.mjs
100%        New File                1058        LICENSE
100%        New File                 576        package.json
100%        New File                 864        readme.md
          New Dir         30    C:\GTPS\login-gurotopia\node_modules\math-intrinsics\
100%        New File                 229        .eslintrc
100%        New File                  18        abs.d.ts
100%        New File                  73        abs.js
100%        New File                1466        CHANGELOG.md
100%        New File                  20        floor.d.ts
100%        New File                  77        floor.js
100%        New File                  80        isFinite.d.ts
100%        New File                 262        isFinite.js
100%        New File                  87        isInteger.d.ts
100%        New File                 410        isInteger.js
100%        New File                  22        isNaN.d.ts
100%        New File                 121        isNaN.js
100%        New File                  79        isNegativeZero.d.ts
100%        New File                 143        isNegativeZero.js
100%        New File                1073        LICENSE
100%        New File                  18        max.d.ts
100%        New File                  73        max.js
100%        New File                  18        min.d.ts
100%        New File                  73        min.js
100%        New File                  76        mod.d.ts
100%        New File                 218        mod.js
100%        New File                2670        package.json
100%        New File                  18        pow.d.ts
100%        New File                  73        pow.js
100%        New File                1884        README.md
100%        New File                  20        round.d.ts
100%        New File                  77        round.js
100%        New File                  57        sign.d.ts
100%        New File                 214        sign.js
100%        New File                  36        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\math-intrinsics\.github\
100%        New File                 561        FUNDING.yml
          New Dir          6    C:\GTPS\login-gurotopia\node_modules\math-intrinsics\constants\
100%        New File                  71        maxArrayLength.d.ts
100%        New File                 110        maxArrayLength.js
100%        New File                  77        maxSafeInteger.d.ts
100%        New File                 231        maxSafeInteger.js
100%        New File                  71        maxValue.d.ts
100%        New File                 197        maxValue.js
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\math-intrinsics\test\
100%        New File                6320        index.js
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\media-typer\
100%        New File                1155        HISTORY.md
100%        New File                3090        index.js
100%        New File                1094        LICENSE
100%        New File                 925        package.json
100%        New File                2992        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\merge-descriptors\
100%        New File                 635        index.d.ts
100%        New File                 616        index.js
100%        New File                1231        license
100%        New File                 961        package.json
100%        New File                 930        readme.md
          New Dir          6    C:\GTPS\login-gurotopia\node_modules\mime-db\
100%        New File              203840        db.json
100%        New File               13886        HISTORY.md
100%        New File                 189        index.js
100%        New File                1172        LICENSE
100%        New File                1530        package.json
100%        New File                4949        README.md
          New Dir          6    C:\GTPS\login-gurotopia\node_modules\mime-types\
100%        New File                9923        HISTORY.md
100%        New File                4546        index.js
100%        New File                1167        LICENSE
100%        New File                1497        mimeScore.js
100%        New File                1266        package.json
100%        New File                4472        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\ms\
100%        New File                3024        index.js
100%        New File                1079        license.md
100%        New File                 732        package.json
100%        New File                1886        readme.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\negotiator\
100%        New File                2619        HISTORY.md
100%        New File                2516        index.js
100%        New File                1177        LICENSE
100%        New File                1080        package.json
100%        New File                5330        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\negotiator\lib\
100%        New File                3081        charset.js
100%        New File                4155        encoding.js
100%        New File                3409        language.js
100%        New File                5343        mediaType.js
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\object-assign\
100%        New File                2108        index.js
100%        New File                1119        license
100%        New File                 764        package.json
100%        New File                1502        readme.md
          New Dir         10    C:\GTPS\login-gurotopia\node_modules\object-inspect\
100%        New File                1298        .eslintrc
100%        New File                 236        .nycrc
100%        New File               36562        CHANGELOG.md
100%        New File               19059        index.js
100%        New File                1071        LICENSE
100%        New File                 365        package-support.json
100%        New File                2841        package.json
100%        New File                2988        readme.markdown
100%        New File                 534        test-core-js.js
100%        New File                  42        util.inspect.js
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\object-inspect\.github\
100%        New File                 585        FUNDING.yml
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\object-inspect\example\
100%        New File                 391        all.js
100%        New File                 116        circular.js
100%        New File                 126        fn.js
100%        New File                 251        inspect.js
          New Dir         18    C:\GTPS\login-gurotopia\node_modules\object-inspect\test\
100%        New File                2082        bigint.js
100%        New File                 451        circular.js
100%        New File                 400        deep.js
100%        New File                1575        element.js
100%        New File                1536        err.js
100%        New File                 683        fakes.js
100%        New File                2227        fn.js
100%        New File                 372        global.js
100%        New File                 514        has.js
100%        New File                 255        holes.js
100%        New File                6633        indent-option.js
100%        New File                4946        inspect.js
100%        New File                 268        lowbyte.js
100%        New File                2312        number.js
100%        New File                1530        quoteStyle.js
100%        New File                1546        toStringTag.js
100%        New File                 302        undef.js
100%        New File                8407        values.js
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\object-inspect\test\browser\
100%        New File                 416        dom.js
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\on-finished\
100%        New File                1865        HISTORY.md
100%        New File                4430        index.js
100%        New File                1167        LICENSE
100%        New File                1057        package.json
100%        New File                5160        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\once\
100%        New File                 765        LICENSE
100%        New File                 935        once.js
100%        New File                 574        package.json
100%        New File                1772        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\parseurl\
100%        New File                1043        HISTORY.md
100%        New File                2809        index.js
100%        New File                1173        LICENSE
100%        New File                1180        package.json
100%        New File                4094        README.md
          New Dir          3    C:\GTPS\login-gurotopia\node_modules\path-to-regexp\
100%        New File                1103        LICENSE
100%        New File                1399        package.json
100%        New File                7850        Readme.md
          New Dir          3    C:\GTPS\login-gurotopia\node_modules\path-to-regexp\dist\
100%        New File                4006        index.d.ts
100%        New File               12833        index.js
100%        New File               29156        index.js.map
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\proxy-addr\
100%        New File                2991        HISTORY.md
100%        New File                6000        index.js
100%        New File                1094        LICENSE
100%        New File                1183        package.json
100%        New File                4131        README.md
          New Dir          7    C:\GTPS\login-gurotopia\node_modules\qs\
100%        New File                 597        .editorconfig
100%        New File                 216        .nycrc
100%        New File               33554        CHANGELOG.md
100%        New File                1450        eslint.config.mjs
100%        New File                1600        LICENSE.md
100%        New File                3151        package.json
100%        New File               25887        README.md
          New Dir          3    C:\GTPS\login-gurotopia\node_modules\qs\.github\
100%        New File                 548        FUNDING.yml
100%        New File                 413        SECURITY.md
100%        New File                4665        THREAT_MODEL.md
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\qs\dist\
100%        New File               50512        qs.js
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\qs\lib\
100%        New File                 476        formats.js
100%        New File                 211        index.js
100%        New File               13255        parse.js
100%        New File               11475        stringify.js
100%        New File                9211        utils.js
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\qs\test\
100%        New File                7698        empty-keys-cases.js
100%        New File               55395        parse.js
100%        New File               53382        stringify.js
100%        New File               13868        utils.js
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\range-parser\
100%        New File                 917        HISTORY.md
100%        New File                2900        index.js
100%        New File                1178        LICENSE
100%        New File                1184        package.json
100%        New File                2278        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\raw-body\
100%        New File                2315        index.d.ts
100%        New File                7171        index.js
100%        New File                1181        LICENSE
100%        New File                1275        package.json
100%        New File                6553        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\router\
100%        New File                6571        HISTORY.md
100%        New File               15866        index.js
100%        New File                1128        LICENSE
100%        New File                1142        package.json
100%        New File               12656        README.md
          New Dir          2    C:\GTPS\login-gurotopia\node_modules\router\lib\
100%        New File                4936        layer.js
100%        New File                4552        route.js
          New Dir          7    C:\GTPS\login-gurotopia\node_modules\safer-buffer\
100%        New File                1483        dangerous.js
100%        New File                1094        LICENSE
100%        New File                 822        package.json
100%        New File               12794        Porting-Buffer.md
100%        New File                8261        Readme.md
100%        New File                2110        safer.js
100%        New File               15735        tests.js
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\send\
100%        New File               20341        index.js
100%        New File                1128        LICENSE
100%        New File                1669        package.json
100%        New File                9062        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\serve-static\
100%        New File                4489        index.js
100%        New File                1189        LICENSE
100%        New File                1193        package.json
100%        New File                7464        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\setprototypeof\
100%        New File                  93        index.d.ts
100%        New File                 407        index.js
100%        New File                 727        LICENSE
100%        New File                1264        package.json
100%        New File                 844        README.md
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\setprototypeof\test\
100%        New File                 690        index.js
          New Dir         10    C:\GTPS\login-gurotopia\node_modules\side-channel\
100%        New File                 145        .editorconfig
100%        New File                 203        .eslintrc
100%        New File                 216        .nycrc
100%        New File               10450        CHANGELOG.md
100%        New File                 486        index.d.ts
100%        New File                1189        index.js
100%        New File                1071        LICENSE
100%        New File                2361        package.json
100%        New File                2152        README.md
100%        New File                 116        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\side-channel\.github\
100%        New File                 583        FUNDING.yml
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\side-channel\test\
100%        New File                2573        index.js
          New Dir         11    C:\GTPS\login-gurotopia\node_modules\side-channel-list\
100%        New File                 145        .editorconfig
100%        New File                 185        .eslintrc
100%        New File                 216        .nycrc
100%        New File                 818        CHANGELOG.md
100%        New File                 335        index.d.ts
100%        New File                3391        index.js
100%        New File                1071        LICENSE
100%        New File                 721        list.d.ts
100%        New File                2257        package.json
100%        New File                2285        README.md
100%        New File                 116        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\side-channel-list\.github\
100%        New File                 588        FUNDING.yml
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\side-channel-list\test\
100%        New File                2613        index.js
          New Dir         10    C:\GTPS\login-gurotopia\node_modules\side-channel-map\
100%        New File                 145        .editorconfig
100%        New File                 185        .eslintrc
100%        New File                 216        .nycrc
100%        New File                1191        CHANGELOG.md
100%        New File                 367        index.d.ts
100%        New File                1981        index.js
100%        New File                1071        LICENSE
100%        New File                2336        package.json
100%        New File                2278        README.md
100%        New File                 116        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\side-channel-map\.github\
100%        New File                 587        FUNDING.yml
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\side-channel-map\test\
100%        New File                2875        index.js
          New Dir         10    C:\GTPS\login-gurotopia\node_modules\side-channel-weakmap\
100%        New File                 145        .editorconfig
100%        New File                 203        .eslintrc
100%        New File                 216        .nycrc
100%        New File                1477        CHANGELOG.md
100%        New File                 382        index.d.ts
100%        New File                2708        index.js
100%        New File                1071        LICENSE
100%        New File                2447        package.json
100%        New File                2342        README.md
100%        New File                 116        tsconfig.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\side-channel-weakmap\.github\
100%        New File                 591        FUNDING.yml
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\side-channel-weakmap\test\
100%        New File                2969        index.js
          New Dir          6    C:\GTPS\login-gurotopia\node_modules\statuses\
100%        New File                1789        codes.json
100%        New File                1628        HISTORY.md
100%        New File                2610        index.js
100%        New File                1172        LICENSE
100%        New File                1440        package.json
100%        New File                3866        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\toidentifier\
100%        New File                 128        HISTORY.md
100%        New File                 504        index.js
100%        New File                1108        LICENSE
100%        New File                1142        package.json
100%        New File                1803        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\type-is\
100%        New File                6864        HISTORY.md
100%        New File                5493        index.js
100%        New File                1172        LICENSE
100%        New File                1236        package.json
100%        New File                6504        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\typescript\
100%        New File                9197        LICENSE.txt
100%        New File                3620        package.json
100%        New File                2842        README.md
100%        New File                2656        SECURITY.md
100%        New File               37824        ThirdPartyNoticeText.txt
          New Dir          2    C:\GTPS\login-gurotopia\node_modules\typescript\bin\
100%        New File                  45        tsc
100%        New File                  50        tsserver
          New Dir        112    C:\GTPS\login-gurotopia\node_modules\typescript\lib\
100%        New File                 992        lib.d.ts
100%        New File               13192        lib.decorators.d.ts
100%        New File                1326        lib.decorators.legacy.d.ts
100%        New File                1887        lib.dom.asynciterable.d.ts
100%        New File               1.7 m        lib.dom.d.ts
100%        New File               29802        lib.dom.iterable.d.ts
100%        New File                5229        lib.es2015.collection.d.ts
100%        New File               22866        lib.es2015.core.d.ts
100%        New File                1241        lib.es2015.d.ts
100%        New File                2557        lib.es2015.generator.d.ts
100%        New File               18200        lib.es2015.iterable.d.ts
100%        New File                3200        lib.es2015.promise.d.ts
100%        New File                5251        lib.es2015.proxy.d.ts
100%        New File                6493        lib.es2015.reflect.d.ts
100%        New File                1649        lib.es2015.symbol.d.ts
100%        New File               11010        lib.es2015.symbol.wellknown.d.ts
100%        New File                5204        lib.es2016.array.include.d.ts
100%        New File                 965        lib.es2016.d.ts
100%        New File                1032        lib.es2016.full.d.ts
100%        New File                1484        lib.es2016.intl.d.ts
100%        New File                 915        lib.es2017.arraybuffer.d.ts
100%        New File                1162        lib.es2017.d.ts
100%        New File                1916        lib.es2017.date.d.ts
100%        New File                1032        lib.es2017.full.d.ts
100%        New File                1449        lib.es2017.intl.d.ts
100%        New File                2473        lib.es2017.object.d.ts
100%        New File                7209        lib.es2017.sharedmemory.d.ts
100%        New File                2378        lib.es2017.string.d.ts
100%        New File                1542        lib.es2017.typedarrays.d.ts
100%        New File                2692        lib.es2018.asyncgenerator.d.ts
100%        New File                2257        lib.es2018.asynciterable.d.ts
100%        New File                1088        lib.es2018.d.ts
100%        New File                1074        lib.es2018.full.d.ts
100%        New File                3021        lib.es2018.intl.d.ts
100%        New File                1353        lib.es2018.promise.d.ts
100%        New File                1232        lib.es2018.regexp.d.ts
100%        New File                3163        lib.es2019.array.d.ts
100%        New File                1071        lib.es2019.d.ts
100%        New File                1074        lib.es2019.full.d.ts
100%        New File                 958        lib.es2019.intl.d.ts
100%        New File                1473        lib.es2019.object.d.ts
100%        New File                1528        lib.es2019.string.d.ts
100%        New File                1006        lib.es2019.symbol.d.ts
100%        New File               38185        lib.es2020.bigint.d.ts
100%        New File                1201        lib.es2020.d.ts
100%        New File                2956        lib.es2020.date.d.ts
100%        New File                1074        lib.es2020.full.d.ts
100%        New File               22438        lib.es2020.intl.d.ts
100%        New File                1587        lib.es2020.number.d.ts
100%        New File                1803        lib.es2020.promise.d.ts
100%        New File                5128        lib.es2020.sharedmemory.d.ts
100%        New File                2556        lib.es2020.string.d.ts
100%        New File                1606        lib.es2020.symbol.wellknown.d.ts
100%        New File                1036        lib.es2021.d.ts
100%        New File                1074        lib.es2021.full.d.ts
100%        New File                8245        lib.es2021.intl.d.ts
100%        New File                2262        lib.es2021.promise.d.ts
100%        New File                1592        lib.es2021.string.d.ts
100%        New File                3171        lib.es2021.weakref.d.ts
100%        New File                4676        lib.es2022.array.d.ts
100%        New File                1108        lib.es2022.d.ts
100%        New File                2379        lib.es2022.error.d.ts
100%        New File                1074        lib.es2022.full.d.ts
100%        New File                7692        lib.es2022.intl.d.ts
100%        New File                1085        lib.es2022.object.d.ts
100%        New File                1331        lib.es2022.regexp.d.ts
100%        New File                1155        lib.es2022.string.d.ts
100%        New File               40236        lib.es2023.array.d.ts
100%        New File                 900        lib.es2023.collection.d.ts
100%        New File                 999        lib.es2023.d.ts
100%        New File                1074        lib.es2023.full.d.ts
100%        New File                2645        lib.es2023.intl.d.ts
100%        New File                2637        lib.es2024.arraybuffer.d.ts
100%        New File                1224        lib.es2024.collection.d.ts
100%        New File                1166        lib.es2024.d.ts
100%        New File                1074        lib.es2024.full.d.ts
100%        New File                1259        lib.es2024.object.d.ts
100%        New File                1389        lib.es2024.promise.d.ts
100%        New File                1073        lib.es2024.regexp.d.ts
100%        New File                3077        lib.es2024.sharedmemory.d.ts
100%        New File                1194        lib.es2024.string.d.ts
100%        New File              218439        lib.es5.d.ts
100%        New File                1032        lib.es6.d.ts
100%        New File                1791        lib.esnext.array.d.ts
100%        New File                3878        lib.esnext.collection.d.ts
100%        New File                1282        lib.esnext.d.ts
100%        New File                1070        lib.esnext.decorators.d.ts
100%        New File                6806        lib.esnext.disposable.d.ts
100%        New File                1029        lib.esnext.error.d.ts
100%        New File               20528        lib.esnext.float16.d.ts
100%        New File                1074        lib.esnext.full.d.ts
100%        New File                 893        lib.esnext.intl.d.ts
100%        New File                8676        lib.esnext.iterator.d.ts
100%        New File                1658        lib.esnext.promise.d.ts
100%        New File                1067        lib.esnext.sharedmemory.d.ts
100%        New File                9451        lib.scripthost.d.ts
100%        New File                1887        lib.webworker.asynciterable.d.ts
100%        New File              609557        lib.webworker.d.ts
100%        New File                1041        lib.webworker.importscripts.d.ts
100%        New File               22768        lib.webworker.iterable.d.ts
100%        New File                 267        tsc.js
100%        New File                 272        tsserver.js
100%        New File                 865        tsserverlibrary.d.ts
100%        New File                1012        tsserverlibrary.js
100%        New File              588085        typescript.d.ts
100%        New File               8.6 m        typescript.js
100%        New File               16788        typesMap.json
100%        New File                 280        typingsInstaller.js
100%        New File                2313        watchGuard.js
100%        New File               5.9 m        _tsc.js
100%        New File               27888        _tsserver.js
100%        New File               10363        _typingsInstaller.js
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\cs\
100%        New File              320453        diagnosticMessages.generated.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\de\
100%        New File              344426        diagnosticMessages.generated.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\es\
100%        New File              340054        diagnosticMessages.generated.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\fr\
100%        New File              346016        diagnosticMessages.generated.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\it\
100%        New File              339409        diagnosticMessages.generated.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\ja\
100%        New File              381398        diagnosticMessages.generated.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\ko\
100%        New File              346139        diagnosticMessages.generated.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\pl\
100%        New File              342111        diagnosticMessages.generated.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\pt-br\
100%        New File              330482        diagnosticMessages.generated.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\ru\
100%        New File              443587        diagnosticMessages.generated.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\tr\
100%        New File              330684        diagnosticMessages.generated.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\zh-cn\
100%        New File              295909        diagnosticMessages.generated.json
          New Dir          1    C:\GTPS\login-gurotopia\node_modules\typescript\lib\zh-tw\
100%        New File              292532        diagnosticMessages.generated.json
          New Dir         45    C:\GTPS\login-gurotopia\node_modules\undici-types\
100%        New File                1162        agent.d.ts
100%        New File                1599        api.d.ts
100%        New File                 957        balanced-pool.d.ts
100%        New File                4120        cache-interceptor.d.ts
100%        New File                1251        cache.d.ts
100%        New File                 456        client-stats.d.ts
100%        New File                5003        client.d.ts
100%        New File                1029        connector.d.ts
100%        New File                 561        content-type.d.ts
100%        New File                 696        cookies.d.ts
100%        New File                1766        diagnostics-channel.d.ts
100%        New File               15586        dispatcher.d.ts
100%        New File                 732        env-http-proxy-agent.d.ts
100%        New File                4439        errors.d.ts
100%        New File                1794        eventsource.d.ts
100%        New File                5651        fetch.d.ts
100%        New File                5004        formdata.d.ts
100%        New File                 275        global-dispatcher.d.ts
100%        New File                 176        global-origin.d.ts
100%        New File                3701        h2c-client.d.ts
100%        New File                 451        handlers.d.ts
100%        New File                3336        header.d.ts
100%        New File                4004        index.d.ts
100%        New File                1988        interceptors.d.ts
100%        New File                1090        LICENSE
100%        New File                3448        mock-agent.d.ts
100%        New File                5558        mock-call-history.d.ts
100%        New File                1065        mock-client.d.ts
100%        New File                 336        mock-errors.d.ts
100%        New File                3931        mock-interceptor.d.ts
100%        New File                1037        mock-pool.d.ts
100%        New File                1193        package.json
100%        New File                 599        patch.d.ts
100%        New File                 663        pool-stats.d.ts
100%        New File                1485        pool.d.ts
100%        New File                 806        proxy-agent.d.ts
100%        New File                1900        readable.d.ts
100%        New File                 455        README.md
100%        New File                 233        retry-agent.d.ts
100%        New File                3262        retry-handler.d.ts
100%        New File                3048        snapshot-agent.d.ts
100%        New File                 623        util.d.ts
100%        New File                 245        utility.d.ts
100%        New File                8725        webidl.d.ts
100%        New File                4692        websocket.d.ts
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\unpipe\
100%        New File                  59        HISTORY.md
100%        New File                1118        index.js
100%        New File                1114        LICENSE
100%        New File                 770        package.json
100%        New File                1250        README.md
          New Dir          5    C:\GTPS\login-gurotopia\node_modules\vary\
100%        New File                 792        HISTORY.md
100%        New File                2930        index.js
100%        New File                1094        LICENSE
100%        New File                1215        package.json
100%        New File                2716        README.md
          New Dir          4    C:\GTPS\login-gurotopia\node_modules\wrappy\
100%        New File                 765        LICENSE
100%        New File                 606        package.json
100%        New File                 685        README.md
100%        New File                 905        wrappy.js
          New Dir          1    C:\GTPS\login-gurotopia\public\
100%        New File              157406        favicon.ico
          New Dir          2    C:\GTPS\login-gurotopia\template\
100%        New File               15267        dashboard.html
100%        New File               14664        dashboard.html.2026-11-11T10-40-25-612Z.bak

------------------------------------------------------------------------------

               Total    Copied   Skipped  Mismatch    FAILED    Extras
    Dirs :       274       274         0         0         0         0
   Files :      1809      1809         0         0         0         0
   Bytes :  274.45 m  274.45 m         0         0         0         0
   Times :   0:00:05   0:00:02                       0:00:00   0:00:02


   Speed :           101.546.700 Bytes/sec.
   Speed :              5810,549 MegaBytes/min.
   Ended : Kamis, 12 November 2026 03.09.21

PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> if ($LASTEXITCODE -ge 8) {
>>     throw "Backup folder GTPS gagal. Robocopy exit code: $LASTEXITCODE"
>> }
PS C:\WINDOWS\system32> $extra = "$destination\External"
PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> New-Item -ItemType Directory -Force -Path $extra | Out-Null
PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> Copy-Item "C:\GTPS\Caddyfile" "$extra\Caddyfile" -ErrorAction SilentlyContinue
PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> Copy-Item "$env:WINDIR\System32\drivers\etc\hosts" "$extra\hosts"
PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> Write-Host "Konfigurasi eksternal disimpan."
Konfigurasi eksternal disimpan.
PS C:\WINDOWS\system32> Compress-Archive `
>>     -Path "$destination\*" `
>>     -DestinationPath "$destination.zip" `
>>     -CompressionLevel Optimal
PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> Get-FileHash "$destination.zip" -Algorithm SHA256 |
>>     Format-List |
>>     Out-File "$destination.zip.sha256.txt"
PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> Write-Host "`nBACKUP SELESAI" -ForegroundColor Green

BACKUP SELESAI
PS C:\WINDOWS\system32> Write-Host "$destination.zip"
C:\GTPS_BACKUPS\Gurotopia_FULL_20261112_030903.zip
PS C:\WINDOWS\system32> Get-Item "$destination.zip"


    Directory: C:\GTPS_BACKUPS


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----  Kamis, 12, 11, 2026     03       54381229 Gurotopia_FULL_20261112_030903.zip
                               .10


PS C:\WINDOWS\system32> Get-Item $dbFile
Get-Item : Cannot find path 'C:\GTPS_BACKUPS\gurotopia_20261112_030903.sql' because it does not exist.
At line:1 char:1
+ Get-Item $dbFile
+ ~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (C:\GTPS_BACKUPS...1112_030903.sql:String) [Get-Item], ItemNotFoundExcep
   tion
    + FullyQualifiedErrorId : PathNotFound,Microsoft.PowerShell.Commands.GetItemCommand

PS C:\WINDOWS\system32> Get-Content "$destination.zip.sha256.txt"


Algorithm : SHA256
Hash      : 1C8B26B89CF90D1BF4D20473C9E452F7F652F27A72001CE475076AE2244D64E1
Path      : C:\GTPS_BACKUPS\Gurotopia_FULL_20261112_030903.zip



PS C:\WINDOWS\system32>
PS C:\WINDOWS\system32> tar -tf "$destination.zip" | Select-Object -First 30
External/Caddyfile
External/hosts
GTPS/Caddyfile
GTPS/Run_Server.bat
GTPS/backups/gurotopia_20261111_040200.sql
GTPS/backups/gurotopia_20261111_040212.sql
GTPS/Gurotopia/.github/
GTPS/Gurotopia/.gitignore
GTPS/Gurotopia/Dockerfile
GTPS/Gurotopia/guest_secret.key
GTPS/Gurotopia/items.dat
GTPS/Gurotopia/libmariadb.dll
GTPS/Gurotopia/LICENSE
GTPS/Gurotopia/main.cpp
GTPS/Gurotopia/main.exe
GTPS/Gurotopia/main.exe.before-role-fix
GTPS/Gurotopia/Makefile
GTPS/Gurotopia/mysql_login.txt
GTPS/Gurotopia/README.md
GTPS/Gurotopia/server_data.php
GTPS/Gurotopia/storage_trace.log
GTPS/Gurotopia/windows-setup.bat
GTPS/Gurotopia/worldlock_storage_debug.log
GTPS/Gurotopia/.github/workflows/make-gcc.yml
GTPS/Gurotopia/.vscode/c_cpp_properties.json
GTPS/Gurotopia/.vscode/launch.json
GTPS/Gurotopia/.vscode/tasks.json
GTPS/Gurotopia/build/main.d
GTPS/Gurotopia/build/main.o
GTPS/Gurotopia/build/include/pch.hpp.d
