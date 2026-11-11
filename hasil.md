PS C:\WINDOWS\system32> Write-Host "`n===== CAPTURE STATUS ====="
>> pktmon status
>>
>> Write-Host "`n===== PACKET COUNTERS ====="
>> pktmon counters
>>
>> Write-Host "`n===== STOP CAPTURE ====="
>> pktmon stop

===== CAPTURE STATUS =====

Collected Data:
    Packet counters, packet capture

Capture Type:
    All packets

Monitored Components:
    All

Packet Filters:
     # Name     Port
     - ----     ----
     1 <empty> 17091

Logger Parameters:
    Logger name:        PktMon
    Logging mode:       Circular
    Log file:           C:\GTPS\GTPS-UDP-17091.etl
    Max file size:      512 MB
    Memory used:        144 MB
    Events lost:        0

Event Providers:
    ID                       Level           Keywords
    --                       -----           --------
    Microsoft-Windows-TCPIP    255 0xffffffffffffffff
    Microsoft-Windows-PktMon     4               0x32

===== PACKET COUNTERS =====
All counters are zero.

===== STOP CAPTURE =====
Flushing logs...
Merging metadata...
Log file: C:\GTPS\GTPS-UDP-17091.etl (No events lost)
PS C:\WINDOWS\system32> pktmon etl2txt C:\GTPS\GTPS-UDP-17091.etl `
>>     --out C:\GTPS\GTPS-UDP-17091.txt
Processing...

Events formatted:    587937
Formatted file:      C:\GTPS\GTPS-UDP-17091.txt
PS C:\WINDOWS\system32> Write-Host "`n===== UDP 17091 PACKETS ====="
>>
>> Select-String `
>>     -Path C:\GTPS\GTPS-UDP-17091.txt `
>>     -Pattern '17091|Drop|drop' |
>>     Select-Object -First 150

===== UDP 17091 PACKETS =====

C:\GTPS\GTPS-UDP-17091.txt:1:[00]3050.3498::2026-11-11 23:43:44.946781100 [MSNT_SystemTrace] Event: Header, BufferSize:
 16777216, Version: 131082, ProviderVersion: 26200, NumberOfProcessors: 4, EndTime: 134388893550947316, TimerResolution
: 156250, MaxFileSize: 512, LogFileMode: 0x4010001, BuffersWritten: 8, StartBuffers: 1, PointerSize: 8, EventsLost: 0,
CPUSpeed: 3192, LoggerName: 0x0, LogFileName: 0x0, TimeZoneInformation: 0, BootTime: 134388481005000000, PerfFreq: 1000
0000, StartTime: 134388890249467811, ReservedFlags: 0x1, BuffersLost: 0, SessionNameString: Relogger, LogFileNameString
: C:\GTPS\GTPS-UDP-17091.etl
C:\GTPS\GTPS-UDP-17091.txt:45978:[02]0004.0288::2026-11-11 23:44:08.561709100 [Microsoft-Windows-TCPIP] Nbl 0xFFFFD305E
5EBC2A0 OOB info (Receive ): TcpIpChecksumNetBufferListInfo 0x10, TcpLargeSendNetBufferListInfo 0x0, Ieee8021QNetBuffer
ListInfo 0x0, NetBufferListHashValue 0x0, NetBufferListHashInfo 0x0, VirtualSubnetInfo 0x0, UdpSegmentationOffloadInfo/
TcpRecvSegCoalesceInfo 0x0, NrtNameResolutionId/UdpRecvSegCoalesceOffloadInfo 0x0
C:\GTPS\GTPS-UDP-17091.txt:47926:[00]0000.0000::2026-11-11 23:44:10.258131000 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:3306, Remote = 127.0.0.1:37258. Rea
son = Duplicate Segment .
C:\GTPS\GTPS-UDP-17091.txt:47927:[03]0000.0000::2026-11-11 23:44:10.258131000 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:3306, Remote = 127.0.0.1:37260. Rea
son = Duplicate Segment .
C:\GTPS\GTPS-UDP-17091.txt:47929:[01]0000.0000::2026-11-11 23:44:10.258132000 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:3306, Remote = 127.0.0.1:37262. Rea
son = Duplicate Segment .
C:\GTPS\GTPS-UDP-17091.txt:47969:[03]0000.0000::2026-11-11 23:44:10.258146700 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:3306, Remote = 127.0.0.1:37261. Rea
son = Duplicate Segment .
C:\GTPS\GTPS-UDP-17091.txt:47970:[01]0000.0000::2026-11-11 23:44:10.258146800 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:3306, Remote = 127.0.0.1:37263. Rea
son = Duplicate Segment .
C:\GTPS\GTPS-UDP-17091.txt:48003:[03]0000.0000::2026-11-11 23:44:10.258156100 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:3306, Remote = 127.0.0.1:37265. Rea
son = Duplicate Segment .
C:\GTPS\GTPS-UDP-17091.txt:48004:[01]0000.0000::2026-11-11 23:44:10.258156100 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:3306, Remote = 127.0.0.1:37266. Rea
son = Duplicate Segment .
C:\GTPS\GTPS-UDP-17091.txt:48037:[01]0000.0000::2026-11-11 23:44:10.258165600 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:3306, Remote = 127.0.0.1:37267. Rea
son = Duplicate Segment .
C:\GTPS\GTPS-UDP-17091.txt:48038:[03]0000.0000::2026-11-11 23:44:10.258165700 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:3306, Remote = 127.0.0.1:37264. Rea
son = Duplicate Segment .
C:\GTPS\GTPS-UDP-17091.txt:48360:[00]1690.1768::2026-11-11 23:44:10.902708000 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol UDP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 239.255.255.250:1900, Remote = 192.168.18.14:
51955. Reason = Session state error .
C:\GTPS\GTPS-UDP-17091.txt:49397:[02]1690.1768::2026-11-11 23:44:11.912552500 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol UDP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 239.255.255.250:1900, Remote = 192.168.18.14:
51955. Reason = Session state error .
C:\GTPS\GTPS-UDP-17091.txt:50659:[02]1690.1768::2026-11-11 23:44:12.913653500 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol UDP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 239.255.255.250:1900, Remote = 192.168.18.14:
51955. Reason = Session state error .
C:\GTPS\GTPS-UDP-17091.txt:51944:[00]1690.1768::2026-11-11 23:44:13.922499700 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol UDP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 239.255.255.250:1900, Remote = 192.168.18.14:
51955. Reason = Session state error .
C:\GTPS\GTPS-UDP-17091.txt:60816:[00]310C.277C::2026-11-11 23:44:19.024416400 [Microsoft-Windows-TCPIP] TCPIP: Transpor
t (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:3306, Remote = 127.0.0.1:37259. Rea
son = Duplicate Segment .
C:\GTPS\GTPS-UDP-17091.txt:95306:[01]0004.0288::2026-11-11 23:44:37.941709100 [Microsoft-Windows-TCPIP] Nbl 0xFFFFD305E
5F29780 OOB info (Receive ): TcpIpChecksumNetBufferListInfo 0x10, TcpLargeSendNetBufferListInfo 0x0, Ieee8021QNetBuffer
ListInfo 0x0, NetBufferListHashValue 0x0, NetBufferListHashInfo 0x0, VirtualSubnetInfo 0x0, UdpSegmentationOffloadInfo/
TcpRecvSegCoalesceInfo 0x0, NrtNameResolutionId/UdpRecvSegCoalesceOffloadInfo 0x0
C:\GTPS\GTPS-UDP-17091.txt:144835:[01]0004.0288::2026-11-11 23:45:03.625632000 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 192.168.18.14:55314, Remote = 192.168.18.1:5
3. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:144836:[01]0004.0288::2026-11-11 23:45:03.625649000 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 192.168.18.14, Remote = 192.168.18.1. Reason
 = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:144837:[01]0004.0288::2026-11-11 23:45:03.625650800 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol UDP , AddressFamily = IPV4 ) dropped 1 packet(s) on interface 13. SourceAddress = 192.168.18.1. DestAd
dress = 192.168.18.14. Reason = Port unreachable . Direction = Receive . NBL = 0xFFFFD305E5F949F0.
C:\GTPS\GTPS-UDP-17091.txt:144840:[01]0004.0288::2026-11-11 23:45:03.625674900 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol ICMP , AddressFamily = IPV4 ) dropped 1 packet(s) on interface 13. SourceAddress = 192.168.18.14. Dest
Address = 192.168.18.1. Reason = Inspection drop . Direction = Send . NBL = 0xFFFFD305F3230540.
C:\GTPS\GTPS-UDP-17091.txt:146755:[01]0004.0288::2026-11-11 23:45:04.150048200 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = [fe80::73d2:db5f:f7bd:6dc0%13]:51306, Remote
 = [fe80::1%13]:53. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:146756:[01]0004.0288::2026-11-11 23:45:04.150064600 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = fe80::73d2:db5f:f7bd:6dc0%13, Remote = fe80:
:1%13. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:146757:[01]0004.0288::2026-11-11 23:45:04.150066400 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::1. DestAddress
 = fe80::73d2:db5f:f7bd:6dc0. Reason = Port unreachable . Direction = Receive . NBL = 0xFFFFD305E5FBC2A0.
C:\GTPS\GTPS-UDP-17091.txt:146760:[01]0004.0288::2026-11-11 23:45:04.150084600 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol ICMPV6 , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::73d2:db5f:f
7bd:6dc0. DestAddress = fe80::1. Reason = Inspection drop . Direction = Send . NBL = 0xFFFFD305F3230540.
C:\GTPS\GTPS-UDP-17091.txt:146981:[00]3314.1B48::2026-11-11 23:45:04.212488200 [Microsoft-Windows-TCPIP] Event: TcpGlob
alRoParameters, addressFamily: 2, ActiveOpens: 3987, PassiveOpens: 1325, AttemptFails: 175, EstabResets: 1544, CurrEsta
b: 32, TimeWaitCollisions: 0, InSegs: 164758, OutSegs: 157023, RetransSegs: 705, OutRsts: 2069, InErrs: 0, NumConns: 33
, BytesBuffered: 0, SendAvailable: 31, SilentModeRcvDrops: 0, SilentModeOutRstDrops: 0, FastopenActiveOpens: 0, Fastope
nPassiveOpens: 0, FastopenAttemptsFailed: 0, FirstSynRexmits: 69, FirstSynRexmitsWithFastopen: 0
C:\GTPS\GTPS-UDP-17091.txt:146995:[00]3314.1B48::2026-11-11 23:45:04.212513100 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:14594, Remote = 127.0.0.1:14595. R
eason = Received RST (subreason 0) .
C:\GTPS\GTPS-UDP-17091.txt:148973:[01]3314.1B48::2026-11-11 23:45:05.293612300 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:14597, Remote = 127.0.0.1:14598. R
eason = Received RST (subreason 0) .
C:\GTPS\GTPS-UDP-17091.txt:149681:[01]0004.0288::2026-11-11 23:45:05.597491700 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = [fe80::73d2:db5f:f7bd:6dc0%13]:52065, Remote
 = [fe80::1%13]:53. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:149682:[01]0004.0288::2026-11-11 23:45:05.597506800 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = fe80::73d2:db5f:f7bd:6dc0%13, Remote = fe80:
:1%13. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:149683:[01]0004.0288::2026-11-11 23:45:05.597508100 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::1. DestAddress
 = fe80::73d2:db5f:f7bd:6dc0. Reason = Port unreachable . Direction = Receive . NBL = 0xFFFFD305E5F24C60.
C:\GTPS\GTPS-UDP-17091.txt:149686:[01]0004.0288::2026-11-11 23:45:05.597524900 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol ICMPV6 , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::73d2:db5f:f
7bd:6dc0. DestAddress = fe80::1. Reason = Inspection drop . Direction = Send . NBL = 0xFFFFD305F3230540.
C:\GTPS\GTPS-UDP-17091.txt:151170:[01]0004.0288::2026-11-11 23:45:05.904963600 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = [fe80::73d2:db5f:f7bd:6dc0%13]:50255, Remote
 = [fe80::1%13]:53. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:151171:[01]0004.0288::2026-11-11 23:45:05.904980000 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = fe80::73d2:db5f:f7bd:6dc0%13, Remote = fe80:
:1%13. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:151172:[01]0004.0288::2026-11-11 23:45:05.904981600 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::1. DestAddress
 = fe80::73d2:db5f:f7bd:6dc0. Reason = Port unreachable . Direction = Receive . NBL = 0xFFFFD305E5FCA780.
C:\GTPS\GTPS-UDP-17091.txt:151173:[01]0004.0288::2026-11-11 23:45:05.904985200 [Microsoft-Windows-TCPIP] ICMPV6 : Send
path drop on interface 13. Type = Destination Unreachable , Code = 4, Reason = Path rate limit , Status = {Data Not Acc
epted}
C:\GTPS\GTPS-UDP-17091.txt:151177:[02]0004.0288::2026-11-11 23:45:05.905909900 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = [fe80::73d2:db5f:f7bd:6dc0%13]:64409, Remote
 = [fe80::1%13]:53. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:151178:[02]0004.0288::2026-11-11 23:45:05.905926400 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = fe80::73d2:db5f:f7bd:6dc0%13, Remote = fe80:
:1%13. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:151179:[02]0004.0288::2026-11-11 23:45:05.905928000 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::1. DestAddress
 = fe80::73d2:db5f:f7bd:6dc0. Reason = Port unreachable . Direction = Receive . NBL = 0xFFFFD305E5F9B2A0.
C:\GTPS\GTPS-UDP-17091.txt:151180:[02]0004.0288::2026-11-11 23:45:05.905931900 [Microsoft-Windows-TCPIP] ICMPV6 : Send
path drop on interface 13. Type = Destination Unreachable , Code = 4, Reason = Path rate limit , Status = {Data Not Acc
epted}
C:\GTPS\GTPS-UDP-17091.txt:151544:[01]3314.24E0::2026-11-11 23:45:05.914185800 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:14613, Remote = 127.0.0.1:14614. R
eason = Received RST (subreason 0) .
C:\GTPS\GTPS-UDP-17091.txt:151691:[01]0004.0288::2026-11-11 23:45:05.917682900 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = [fe80::73d2:db5f:f7bd:6dc0%13]:61179, Remote
 = [fe80::1%13]:53. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:151692:[01]0004.0288::2026-11-11 23:45:05.917698100 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = fe80::73d2:db5f:f7bd:6dc0%13, Remote = fe80:
:1%13. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:151693:[01]0004.0288::2026-11-11 23:45:05.917699500 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::1. DestAddress
 = fe80::73d2:db5f:f7bd:6dc0. Reason = Port unreachable . Direction = Receive . NBL = 0xFFFFD305E5FB6030.
C:\GTPS\GTPS-UDP-17091.txt:151694:[01]0004.0288::2026-11-11 23:45:05.917702900 [Microsoft-Windows-TCPIP] ICMPV6 : Send
path drop on interface 13. Type = Destination Unreachable , Code = 4, Reason = Path rate limit , Status = {Data Not Acc
epted}
C:\GTPS\GTPS-UDP-17091.txt:152599:[00]36A4.2810::2026-11-11 23:45:05.927692300 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:14616, Remote = 127.0.0.1:8443. Re
ason = Received RST (subreason 0) .
C:\GTPS\GTPS-UDP-17091.txt:152785:[02]3314.24E0::2026-11-11 23:45:05.928365900 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:443, Remote = 127.0.0.1:14615. Rea
son = Received RST (subreason 0) .
C:\GTPS\GTPS-UDP-17091.txt:152859:[02]3314.24E0::2026-11-11 23:45:05.928491600 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:14611, Remote = 127.0.0.1:14612. R
eason = FIN-WAIT2 .
C:\GTPS\GTPS-UDP-17091.txt:153220:[02]0004.0288::2026-11-11 23:45:05.952205800 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = [fe80::73d2:db5f:f7bd:6dc0%13]:60277, Remote
 = [fe80::1%13]:53. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:153221:[02]0004.0288::2026-11-11 23:45:05.952223300 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = fe80::73d2:db5f:f7bd:6dc0%13, Remote = fe80:
:1%13. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:153222:[02]0004.0288::2026-11-11 23:45:05.952224500 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::1. DestAddress
 = fe80::73d2:db5f:f7bd:6dc0. Reason = Port unreachable . Direction = Receive . NBL = 0xFFFFD305E5FA3780.
C:\GTPS\GTPS-UDP-17091.txt:153223:[02]0004.0288::2026-11-11 23:45:05.952227500 [Microsoft-Windows-TCPIP] ICMPV6 : Send
path drop on interface 13. Type = Destination Unreachable , Code = 4, Reason = Path rate limit , Status = {Data Not Acc
epted}
C:\GTPS\GTPS-UDP-17091.txt:153233:[02]0004.0288::2026-11-11 23:45:05.952776000 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = [fe80::73d2:db5f:f7bd:6dc0%13]:64907, Remote
 = [fe80::1%13]:53. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:153234:[02]0004.0288::2026-11-11 23:45:05.952784700 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = fe80::73d2:db5f:f7bd:6dc0%13, Remote = fe80:
:1%13. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:153235:[02]0004.0288::2026-11-11 23:45:05.952785700 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::1. DestAddress
 = fe80::73d2:db5f:f7bd:6dc0. Reason = Port unreachable . Direction = Receive . NBL = 0xFFFFD305E5FCD780.
C:\GTPS\GTPS-UDP-17091.txt:153236:[02]0004.0288::2026-11-11 23:45:05.952787600 [Microsoft-Windows-TCPIP] ICMPV6 : Send
path drop on interface 13. Type = Destination Unreachable , Code = 4, Reason = Path rate limit , Status = {Data Not Acc
epted}
C:\GTPS\GTPS-UDP-17091.txt:154592:[00]0004.0288::2026-11-11 23:45:06.334464800 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 192.168.18.14:14604, Remote = 104.83.196.8:4
43. Reason = Duplicate Segment .
C:\GTPS\GTPS-UDP-17091.txt:154722:[00]3314.1B48::2026-11-11 23:45:06.335359400 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:14592, Remote = 127.0.0.1:14593. R
eason = FIN-WAIT2 .
C:\GTPS\GTPS-UDP-17091.txt:155094:[02]0004.0288::2026-11-11 23:45:06.399037900 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = [fe80::73d2:db5f:f7bd:6dc0%13]:54412, Remote
 = [fe80::1%13]:53. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:155095:[02]0004.0288::2026-11-11 23:45:06.399072700 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = fe80::73d2:db5f:f7bd:6dc0%13, Remote = fe80:
:1%13. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:155096:[02]0004.0288::2026-11-11 23:45:06.399074800 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::1. DestAddress
 = fe80::73d2:db5f:f7bd:6dc0. Reason = Port unreachable . Direction = Receive . NBL = 0xFFFFD305E5F9E780.
C:\GTPS\GTPS-UDP-17091.txt:155097:[02]0004.0288::2026-11-11 23:45:06.399078100 [Microsoft-Windows-TCPIP] ICMPV6 : Send
path drop on interface 13. Type = Destination Unreachable , Code = 4, Reason = Path rate limit , Status = {Data Not Acc
epted}
C:\GTPS\GTPS-UDP-17091.txt:157570:[01]1270.339C::2026-11-11 23:45:06.775378400 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:48640, Remote = 127.0.0.1:8443. Re
ason = Received RST (subreason 0) .
C:\GTPS\GTPS-UDP-17091.txt:157691:[03]3314.0718::2026-11-11 23:45:06.793902000 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E94860 (LocalAddress = 0.0.0.0:53883, RemoteAddress = 127.0.0.1:17091) sending 1 messages and a total of 44
 bytes. PID = 13076 ProcessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:157692:[03]3314.0718::2026-11-11 23:45:06.793935900 [Microsoft-Windows-TCPIP] WFP-ALE: Remot
eEndPoint Insertion: (local=127.0.0.1:53883 remote=127.0.0.1:17091) PartitionId=1 PartitionNumEntries=2
C:\GTPS\GTPS-UDP-17091.txt:157693:[03]3314.0718::2026-11-11 23:45:06.793954000 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F454FC60. Interface=1, Compartment=1, Src=127.0.0.1:53883, Dst=127.0.0.1:17091, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:157695:[03]3314.0718::2026-11-11 23:45:06.794000800 [Microsoft-Windows-TCPIP] WFP-ALE: Remot
eEndPoint Insertion: (local=127.0.0.1:17091 remote=127.0.0.1:53883) PartitionId=3 PartitionNumEntries=3
C:\GTPS\GTPS-UDP-17091.txt:157697:[03]3314.0718::2026-11-11 23:45:06.794009000 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 127.0.0.1:17091, RemoteAddress = 127.0.0.1:53883) delivering 44 bytes. PID = 13988 P
rocessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:157700:[01]36A4.1950::2026-11-11 23:45:06.794074700 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 0.0.0.0:17091, RemoteAddress = 127.0.0.1:53883) sending 1 messages and a total of 33
 bytes. PID = 13988 ProcessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:157701:[01]36A4.1950::2026-11-11 23:45:06.794085000 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305EDB94C60. Interface=1, Compartment=1, Src=127.0.0.1:17091, Dst=127.0.0.1:53883, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:157704:[01]36A4.1950::2026-11-11 23:45:06.794094000 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E94860 (LocalAddress = 127.0.0.1:53883, RemoteAddress = 127.0.0.1:17091) delivering 33 bytes. PID = 13076 P
rocessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:157842:[00]1270.3120::2026-11-11 23:45:06.801892400 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol TCP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:443, Remote = 127.0.0.1:48638. Rea
son = Received RST (subreason 0) .
C:\GTPS\GTPS-UDP-17091.txt:157854:[03]3314.0718::2026-11-11 23:45:06.808781900 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E94860 (LocalAddress = 0.0.0.0:53883, RemoteAddress = 127.0.0.1:17091) sending 1 messages and a total of 26
 bytes. PID = 13076 ProcessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:157855:[03]3314.0718::2026-11-11 23:45:06.808801600 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F454FC60. Interface=1, Compartment=1, Src=127.0.0.1:53883, Dst=127.0.0.1:17091, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:157858:[03]3314.0718::2026-11-11 23:45:06.808815800 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 127.0.0.1:17091, RemoteAddress = 127.0.0.1:53883) delivering 26 bytes. PID = 13988 P
rocessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:157861:[01]36A4.1950::2026-11-11 23:45:06.809018000 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 0.0.0.0:17091, RemoteAddress = 127.0.0.1:53883) sending 1 messages and a total of 25
 bytes. PID = 13988 ProcessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:157862:[01]36A4.1950::2026-11-11 23:45:06.809031600 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305EDB94C60. Interface=1, Compartment=1, Src=127.0.0.1:17091, Dst=127.0.0.1:53883, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:157865:[01]36A4.1950::2026-11-11 23:45:06.809043300 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E94860 (LocalAddress = 127.0.0.1:53883, RemoteAddress = 127.0.0.1:17091) delivering 25 bytes. PID = 13076 P
rocessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:157868:[03]3314.0718::2026-11-11 23:45:06.809567400 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E94860 (LocalAddress = 0.0.0.0:53883, RemoteAddress = 127.0.0.1:17091) sending 1 messages and a total of 20
 bytes. PID = 13076 ProcessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:157869:[03]3314.0718::2026-11-11 23:45:06.809581700 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F454FC60. Interface=1, Compartment=1, Src=127.0.0.1:53883, Dst=127.0.0.1:17091, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:157872:[03]3314.0718::2026-11-11 23:45:06.809592100 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 127.0.0.1:17091, RemoteAddress = 127.0.0.1:53883) delivering 20 bytes. PID = 13988 P
rocessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:157875:[03]3314.0718::2026-11-11 23:45:06.809756700 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E94860 (LocalAddress = 0.0.0.0:53883, RemoteAddress = 127.0.0.1:17091) sending 1 messages and a total of 72
0 bytes. PID = 13076 ProcessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:157876:[03]3314.0718::2026-11-11 23:45:06.809763000 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F454FC60. Interface=1, Compartment=1, Src=127.0.0.1:53883, Dst=127.0.0.1:17091, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:157879:[03]3314.0718::2026-11-11 23:45:06.809768800 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 127.0.0.1:17091, RemoteAddress = 127.0.0.1:53883) delivering 720 bytes. PID = 13988
ProcessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:157882:[01]36A4.1950::2026-11-11 23:45:06.810108700 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 0.0.0.0:17091, RemoteAddress = 127.0.0.1:53883) sending 1 messages and a total of 14
 bytes. PID = 13988 ProcessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:157883:[01]36A4.1950::2026-11-11 23:45:06.810120400 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305EDB94C60. Interface=1, Compartment=1, Src=127.0.0.1:17091, Dst=127.0.0.1:53883, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:157886:[01]36A4.1950::2026-11-11 23:45:06.810129200 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E94860 (LocalAddress = 127.0.0.1:53883, RemoteAddress = 127.0.0.1:17091) delivering 14 bytes. PID = 13076 P
rocessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:157928:[02]0004.0288::2026-11-11 23:45:06.815734500 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = [fe80::73d2:db5f:f7bd:6dc0%13]:61075, Remote
 = [fe80::1%13]:53. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:157939:[02]0004.0288::2026-11-11 23:45:06.815790300 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = fe80::73d2:db5f:f7bd:6dc0%13, Remote = fe80:
:1%13. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:157940:[02]0004.0288::2026-11-11 23:45:06.815791900 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::1. DestAddress
 = fe80::73d2:db5f:f7bd:6dc0. Reason = Port unreachable . Direction = Receive . NBL = 0xFFFFD305E5EBF780.
C:\GTPS\GTPS-UDP-17091.txt:157943:[02]0004.0288::2026-11-11 23:45:06.815817300 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol ICMPV6 , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::73d2:db5f:f
7bd:6dc0. DestAddress = fe80::1. Reason = Inspection drop . Direction = Send . NBL = 0xFFFFD305F44B7350.
C:\GTPS\GTPS-UDP-17091.txt:160461:[01]36A4.1950::2026-11-11 23:45:06.825294900 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 0.0.0.0:17091, RemoteAddress = 127.0.0.1:53883) sending 1 messages and a total of 89
 bytes. PID = 13988 ProcessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:160462:[01]36A4.1950::2026-11-11 23:45:06.825308900 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305EDB94C60. Interface=1, Compartment=1, Src=127.0.0.1:17091, Dst=127.0.0.1:53883, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:160465:[01]36A4.1950::2026-11-11 23:45:06.825321100 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E94860 (LocalAddress = 127.0.0.1:53883, RemoteAddress = 127.0.0.1:17091) delivering 89 bytes. PID = 13076 P
rocessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:160468:[03]3314.0718::2026-11-11 23:45:06.830895600 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E94860 (LocalAddress = 0.0.0.0:53883, RemoteAddress = 127.0.0.1:17091) sending 1 messages and a total of 20
 bytes. PID = 13076 ProcessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:160469:[03]3314.0718::2026-11-11 23:45:06.830913900 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F454FC60. Interface=1, Compartment=1, Src=127.0.0.1:53883, Dst=127.0.0.1:17091, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:160472:[03]3314.0718::2026-11-11 23:45:06.830927600 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 127.0.0.1:17091, RemoteAddress = 127.0.0.1:53883) delivering 20 bytes. PID = 13988 P
rocessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:160496:[03]3314.0718::2026-11-11 23:45:06.849653800 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E94860 (LocalAddress = 0.0.0.0:53883, RemoteAddress = 127.0.0.1:17091) sending 1 messages and a total of 32
 bytes. PID = 13076 ProcessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:160497:[03]3314.0718::2026-11-11 23:45:06.849668000 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F454FC60. Interface=1, Compartment=1, Src=127.0.0.1:53883, Dst=127.0.0.1:17091, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:160500:[03]3314.0718::2026-11-11 23:45:06.849679000 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 127.0.0.1:17091, RemoteAddress = 127.0.0.1:53883) delivering 32 bytes. PID = 13988 P
rocessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:160502:[03]3314.0718::2026-11-11 23:45:06.849724200 [Microsoft-Windows-TCPIP] WFP-ALE: Remot
eEndPoint Deletion: (local=127.0.0.1:53883 remote=127.0.0.1:17091) PartitionId=1 PartitionNumEntries=1
C:\GTPS\GTPS-UDP-17091.txt:160505:[00]36A4.1950::2026-11-11 23:45:06.849726800 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 0.0.0.0:17091, RemoteAddress = 127.0.0.1:53883) sending 1 messages and a total of 14
 bytes. PID = 13988 ProcessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:160506:[00]36A4.1950::2026-11-11 23:45:06.849735500 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F343B030. Interface=1, Compartment=1, Src=127.0.0.1:17091, Dst=127.0.0.1:53883, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:160508:[00]36A4.1950::2026-11-11 23:45:06.849738300 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1:53883, Remote = 127.0.0.1:17091. R
eason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:160509:[00]36A4.1950::2026-11-11 23:45:06.849742600 [Microsoft-Windows-PktMon] Drop: PktGrou
pId 38655, PktNumber 1, Appearance 0, Direction Rx , Type IP , Component 9, Filter 1, DropReason INET: transport endpoi
nt was not found , DropLocation 0xE000460A, OriginalSize 42, LoggedSize 42
C:\GTPS\GTPS-UDP-17091.txt:160510:      Drop: ip: 127.0.0.1.17091 > 127.0.0.1.53883: UDP, length 14
C:\GTPS\GTPS-UDP-17091.txt:160511:[00]36A4.1950::2026-11-11 23:45:06.849748200 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV4 ) dropped 1 packet(s) with Local = 127.0.0.1, Remote = 127.0.0.1. Reason = Tran
sport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:160512:[00]36A4.1950::2026-11-11 23:45:06.849748900 [Microsoft-Windows-PktMon] Drop: PktGrou
pId 38656, PktNumber 1, Appearance 0, Direction Rx , Type IP , Component 9, Filter 1, DropReason INET: transport endpoi
nt was not found , DropLocation 0xE0004704, OriginalSize 42, LoggedSize 42
C:\GTPS\GTPS-UDP-17091.txt:160513:      Drop: ip: 127.0.0.1.17091 > 127.0.0.1.53883: UDP, length 14
C:\GTPS\GTPS-UDP-17091.txt:160514:[00]36A4.1950::2026-11-11 23:45:06.849750400 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol UDP , AddressFamily = IPV4 ) dropped 1 packet(s) on interface 1. SourceAddress = 127.0.0.1. DestAddres
s = 127.0.0.1. Reason = Port unreachable . Direction = Receive . NBL = 0xFFFFD305F343B030.
C:\GTPS\GTPS-UDP-17091.txt:160515:[00]36A4.1950::2026-11-11 23:45:06.849751800 [Microsoft-Windows-PktMon] Drop: PktGrou
pId 38657, PktNumber 1, Appearance 0, Direction Rx , Type IP , Component 9, Filter 1, DropReason Port unreachable , Dro
pLocation 0xE0004134, OriginalSize 42, LoggedSize 42
C:\GTPS\GTPS-UDP-17091.txt:160516:      Drop: ip: 127.0.0.1.17091 > 127.0.0.1.53883: UDP, length 14
C:\GTPS\GTPS-UDP-17091.txt:160566:[03]3314.0718::2026-11-11 23:45:06.849947100 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E927E0 (LocalAddress = 0.0.0.0:53884, RemoteAddress = 127.0.0.1:17091) sending 1 messages and a total of 44
 bytes. PID = 13076 ProcessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:160567:[03]3314.0718::2026-11-11 23:45:06.849974300 [Microsoft-Windows-TCPIP] WFP-ALE: Remot
eEndPoint Insertion: (local=127.0.0.1:53884 remote=127.0.0.1:17091) PartitionId=3 PartitionNumEntries=4
C:\GTPS\GTPS-UDP-17091.txt:160568:[03]3314.0718::2026-11-11 23:45:06.849986700 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F454FC60. Interface=1, Compartment=1, Src=127.0.0.1:53884, Dst=127.0.0.1:17091, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:160570:[03]3314.0718::2026-11-11 23:45:06.850028000 [Microsoft-Windows-TCPIP] WFP-ALE: Remot
eEndPoint Insertion: (local=127.0.0.1:17091 remote=127.0.0.1:53884) PartitionId=1 PartitionNumEntries=2
C:\GTPS\GTPS-UDP-17091.txt:160572:[03]3314.0718::2026-11-11 23:45:06.850035600 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 127.0.0.1:17091, RemoteAddress = 127.0.0.1:53884) delivering 44 bytes. PID = 13988 P
rocessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:160710:[00]36A4.1950::2026-11-11 23:45:06.851985100 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 0.0.0.0:17091, RemoteAddress = 127.0.0.1:53884) sending 1 messages and a total of 35
 bytes. PID = 13988 ProcessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:160711:[00]36A4.1950::2026-11-11 23:45:06.851998300 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F343B030. Interface=1, Compartment=1, Src=127.0.0.1:17091, Dst=127.0.0.1:53884, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:160714:[00]36A4.1950::2026-11-11 23:45:06.852007800 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E927E0 (LocalAddress = 127.0.0.1:53884, RemoteAddress = 127.0.0.1:17091) delivering 35 bytes. PID = 13076 P
rocessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:160764:[03]3314.0718::2026-11-11 23:45:06.865708200 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E927E0 (LocalAddress = 0.0.0.0:53884, RemoteAddress = 127.0.0.1:17091) sending 1 messages and a total of 26
 bytes. PID = 13076 ProcessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:160765:[03]3314.0718::2026-11-11 23:45:06.865722100 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F454FC60. Interface=1, Compartment=1, Src=127.0.0.1:53884, Dst=127.0.0.1:17091, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:160768:[03]3314.0718::2026-11-11 23:45:06.865736600 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 127.0.0.1:17091, RemoteAddress = 127.0.0.1:53884) delivering 26 bytes. PID = 13988 P
rocessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:160771:[02]36A4.1950::2026-11-11 23:45:06.865798600 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 0.0.0.0:17091, RemoteAddress = 127.0.0.1:53884) sending 1 messages and a total of 25
 bytes. PID = 13988 ProcessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:160772:[02]36A4.1950::2026-11-11 23:45:06.865807900 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F3228C60. Interface=1, Compartment=1, Src=127.0.0.1:17091, Dst=127.0.0.1:53884, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:160775:[02]36A4.1950::2026-11-11 23:45:06.865816400 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E927E0 (LocalAddress = 127.0.0.1:53884, RemoteAddress = 127.0.0.1:17091) delivering 25 bytes. PID = 13076 P
rocessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:160900:[03]3314.0718::2026-11-11 23:45:06.881927000 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E927E0 (LocalAddress = 0.0.0.0:53884, RemoteAddress = 127.0.0.1:17091) sending 1 messages and a total of 20
 bytes. PID = 13076 ProcessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:160901:[03]3314.0718::2026-11-11 23:45:06.881941100 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F454FC60. Interface=1, Compartment=1, Src=127.0.0.1:53884, Dst=127.0.0.1:17091, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:160904:[03]3314.0718::2026-11-11 23:45:06.881958900 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 127.0.0.1:17091, RemoteAddress = 127.0.0.1:53884) delivering 20 bytes. PID = 13988 P
rocessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:161631:[01]0004.0288::2026-11-11 23:45:06.949174900 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = [fe80::73d2:db5f:f7bd:6dc0%13]:64221, Remote
 = [fe80::1%13]:53. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:161632:[00]0004.0288::2026-11-11 23:45:06.949260600 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = fe80::73d2:db5f:f7bd:6dc0%13, Remote = fe80:
:1%13. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:161633:[00]0004.0288::2026-11-11 23:45:06.949263300 [Microsoft-Windows-TCPIP] TCPIP: Network
 layer (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) on interface 13. SourceAddress = fe80::1. DestAddress
 = fe80::73d2:db5f:f7bd:6dc0. Reason = Port unreachable . Direction = Receive . NBL = 0xFFFFD305E5F23780.
C:\GTPS\GTPS-UDP-17091.txt:161634:[00]0004.0288::2026-11-11 23:45:06.949267900 [Microsoft-Windows-TCPIP] ICMPV6 : Send
path drop on interface 13. Type = Destination Unreachable , Code = 4, Reason = Path rate limit , Status = {Data Not Acc
epted}
C:\GTPS\GTPS-UDP-17091.txt:161667:[03]3314.0718::2026-11-11 23:45:06.952839700 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E927E0 (LocalAddress = 0.0.0.0:53884, RemoteAddress = 127.0.0.1:17091) sending 1 messages and a total of 39
6 bytes. PID = 13076 ProcessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:161668:[03]3314.0718::2026-11-11 23:45:06.952858400 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F454FC60. Interface=1, Compartment=1, Src=127.0.0.1:53884, Dst=127.0.0.1:17091, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:161671:[03]3314.0718::2026-11-11 23:45:06.952872300 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 127.0.0.1:17091, RemoteAddress = 127.0.0.1:53884) delivering 396 bytes. PID = 13988
ProcessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:161674:[02]36A4.1950::2026-11-11 23:45:06.953011600 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 0.0.0.0:17091, RemoteAddress = 127.0.0.1:53884) sending 1 messages and a total of 14
 bytes. PID = 13988 ProcessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:161675:[02]36A4.1950::2026-11-11 23:45:06.953023400 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F4497C60. Interface=1, Compartment=1, Src=127.0.0.1:17091, Dst=127.0.0.1:53884, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:161678:[02]36A4.1950::2026-11-11 23:45:06.953032900 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E927E0 (LocalAddress = 127.0.0.1:53884, RemoteAddress = 127.0.0.1:17091) delivering 14 bytes. PID = 13076 P
rocessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:161688:[01]36A4.1950::2026-11-11 23:45:06.956960600 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 0.0.0.0:17091, RemoteAddress = 127.0.0.1:53884) sending 1 messages and a total of 36
 bytes. PID = 13988 ProcessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:161689:[01]36A4.1950::2026-11-11 23:45:06.956974900 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F323E5B0. Interface=1, Compartment=1, Src=127.0.0.1:17091, Dst=127.0.0.1:53884, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:161692:[01]36A4.1950::2026-11-11 23:45:06.956987500 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E927E0 (LocalAddress = 127.0.0.1:53884, RemoteAddress = 127.0.0.1:17091) delivering 36 bytes. PID = 13076 P
rocessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:161695:[03]3314.0718::2026-11-11 23:45:06.973440900 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E927E0 (LocalAddress = 0.0.0.0:53884, RemoteAddress = 127.0.0.1:17091) sending 1 messages and a total of 20
 bytes. PID = 13076 ProcessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:161696:[03]3314.0718::2026-11-11 23:45:06.973459500 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F454FC60. Interface=1, Compartment=1, Src=127.0.0.1:53884, Dst=127.0.0.1:17091, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:161699:[03]3314.0718::2026-11-11 23:45:06.973473500 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 127.0.0.1:17091, RemoteAddress = 127.0.0.1:53884) delivering 20 bytes. PID = 13988 P
rocessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:161702:[02]36A4.1950::2026-11-11 23:45:06.973520500 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F12225E0 (LocalAddress = 0.0.0.0:17091, RemoteAddress = 127.0.0.1:53884) sending 1 messages and a total of 16
 bytes. PID = 13988 ProcessSeqNum 71494644084524890.
C:\GTPS\GTPS-UDP-17091.txt:161703:[02]36A4.1950::2026-11-11 23:45:06.973531300 [Microsoft-Windows-TCPIP] IP: Transmitti
ng loopback Nbl 0xFFFFD305F3228C60. Interface=1, Compartment=1, Src=127.0.0.1:17091, Dst=127.0.0.1:53884, Proto=UDP .
C:\GTPS\GTPS-UDP-17091.txt:161706:[02]36A4.1950::2026-11-11 23:45:06.973541500 [Microsoft-Windows-TCPIP] UDP: endpoint
0xFFFFD305F0E927E0 (LocalAddress = 127.0.0.1:53884, RemoteAddress = 127.0.0.1:17091) delivering 16 bytes. PID = 13076 P
rocessSeqNum 71494644084525027.
C:\GTPS\GTPS-UDP-17091.txt:161711:[03]0004.0288::2026-11-11 23:45:06.982968600 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = [fe80::73d2:db5f:f7bd:6dc0%13]:51931, Remote
 = [fe80::1%13]:53. Reason = Transport endpoint was not found .
C:\GTPS\GTPS-UDP-17091.txt:161712:[03]0004.0288::2026-11-11 23:45:06.982985800 [Microsoft-Windows-TCPIP] TCPIP: Transpo
rt (Protocol UDP , AddressFamily = IPV6 ) dropped 1 packet(s) with Local = fe80::73d2:db5f:f7bd:6dc0%13, Remote = fe80:
:1%13. Reason = Transport endpoint was not found .


PS C:\WINDOWS\system32> Get-Item C:\GTPS\GTPS-UDP-17091.etl
>> Get-Item C:\GTPS\GTPS-UDP-17091.txt


    Directory: C:\GTPS


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----  Rabu, 11, 11, 2026     23.        8597790 GTPS-UDP-17091.etl
                                49
-a----  Rabu, 11, 11, 2026     23.      353814944 GTPS-UDP-17091.txt
