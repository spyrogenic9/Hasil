PS C:\WINDOWS\system32> pktmon stop
>> pktmon filter remove
>> pktmon filter add GTPS-GAME-UDP -t UDP -p 17091
>>
>> pktmon filter list
Packet Monitor is not running.
Removed all filters.
Filter added.
Packet Filters:
     # Name          Protocol  Port
     - ----          --------  ----
     1 GTPS-GAME-UDP UDP      17091
PS C:\WINDOWS\system32> pktmon start --capture `
>>     --file-name C:\GTPS\GTPS-UDP-17091.etl `
>>     --pkt-size 0

Logger Parameters:
    Logger name:        PktMon
    Logging mode:       Circular
    Log file:           C:\GTPS\GTPS-UDP-17091.etl
    Max file size:      512 MB
    Memory used:        128 MB

Collected Data:
    Packet counters, packet capture

Capture Type:
    All packets

Monitored Components:
    All

Packet Filters:
     # Name          Protocol  Port
     - ----          --------  ----
     1 GTPS-GAME-UDP UDP      17091
PS C:\WINDOWS\system32> pktmon counters
>> pktmon stop
>>
>> pktmon etl2txt C:\GTPS\GTPS-UDP-17091.etl `
>>     --out C:\GTPS\GTPS-UDP-17091.txt `
>>     --verbose 3 --hex
>>
>> Write-Host "`n===== HASIL UDP GAME ====="
>>
>> Get-Content C:\GTPS\GTPS-UDP-17091.txt -Tail 120
All counters are zero.
Flushing logs...
Merging metadata...
Log file: C:\GTPS\GTPS-UDP-17091.etl (No events lost)
Processing...

Events formatted:    135
Formatted file:      C:\GTPS\GTPS-UDP-17091.txt

===== HASIL UDP GAME =====
[01]24D8.06B4::2026-11-11 23:53:27.322388400 [Microsoft-Windows-PktMon] Component 19, Type HTTP Protocol , Name http.sys, HTTP
[01]24D8.06B4::2026-11-11 23:53:27.322388700 [Microsoft-Windows-PktMon] Property: Component 19, IP Address  = 2404:8000:1122:7c1:ffcf:5dbf:b248:3661
[01]24D8.06B4::2026-11-11 23:53:27.322389000 [Microsoft-Windows-PktMon] Property: Component 19, MiniportIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322389500 [Microsoft-Windows-PktMon] Drop Counters: Component 19, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322390200 [Microsoft-Windows-PktMon] Flow Counters: Component 19, Edge Upper, Edge Id 2, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322390900 [Microsoft-Windows-PktMon] Flow Counters: Component 19, Edge Lower, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322391500 [Microsoft-Windows-PktMon] Component 18, Type HTTP Protocol , Name http.sys, HTTP
[01]24D8.06B4::2026-11-11 23:53:27.322392000 [Microsoft-Windows-PktMon] Property: Component 18, IP Address  = 2404:8000:1122:7c1:b95d:74ab:15ad:87df
[01]24D8.06B4::2026-11-11 23:53:27.322392500 [Microsoft-Windows-PktMon] Property: Component 18, MiniportIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322393900 [Microsoft-Windows-PktMon] Drop Counters: Component 18, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322394900 [Microsoft-Windows-PktMon] Flow Counters: Component 18, Edge Upper, Edge Id 2, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322395400 [Microsoft-Windows-PktMon] Flow Counters: Component 18, Edge Lower, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322395900 [Microsoft-Windows-PktMon] Component 17, Type HTTP Protocol , Name http.sys, HTTP
[01]24D8.06B4::2026-11-11 23:53:27.322396100 [Microsoft-Windows-PktMon] Property: Component 17, IP Address  = ::1
[01]24D8.06B4::2026-11-11 23:53:27.322396500 [Microsoft-Windows-PktMon] Property: Component 17, MiniportIfIndex  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322396900 [Microsoft-Windows-PktMon] Drop Counters: Component 17, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322397400 [Microsoft-Windows-PktMon] Flow Counters: Component 17, Edge Upper, Edge Id 2, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322397900 [Microsoft-Windows-PktMon] Flow Counters: Component 17, Edge Lower, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322398300 [Microsoft-Windows-PktMon] Component 16, Type HTTP Protocol , Name http.sys, HTTP
[01]24D8.06B4::2026-11-11 23:53:27.322398500 [Microsoft-Windows-PktMon] Property: Component 16, IP Address  = 192.168.18.14
[01]24D8.06B4::2026-11-11 23:53:27.322398800 [Microsoft-Windows-PktMon] Property: Component 16, MiniportIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322399200 [Microsoft-Windows-PktMon] Drop Counters: Component 16, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322399700 [Microsoft-Windows-PktMon] Flow Counters: Component 16, Edge Upper, Edge Id 2, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322400200 [Microsoft-Windows-PktMon] Flow Counters: Component 16, Edge Lower, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322400600 [Microsoft-Windows-PktMon] Component 15, Type HTTP Protocol , Name http.sys, HTTP
[01]24D8.06B4::2026-11-11 23:53:27.322400800 [Microsoft-Windows-PktMon] Property: Component 15, IP Address  = 127.0.0.1
[01]24D8.06B4::2026-11-11 23:53:27.322401100 [Microsoft-Windows-PktMon] Property: Component 15, MiniportIfIndex  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322401600 [Microsoft-Windows-PktMon] Drop Counters: Component 15, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322402200 [Microsoft-Windows-PktMon] Flow Counters: Component 15, Edge Upper, Edge Id 2, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322402700 [Microsoft-Windows-PktMon] Flow Counters: Component 15, Edge Lower, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322403400 [Microsoft-Windows-PktMon] Component 14, Type NetCx , Name rtcx21x64.sys, Realtek PCIe GbE Family Controller
[01]24D8.06B4::2026-11-11 23:53:27.322403800 [Microsoft-Windows-PktMon] Property: Component 14, PhysAddress  = 0x2CF05D056CC7
[01]24D8.06B4::2026-11-11 23:53:27.322404200 [Microsoft-Windows-PktMon] Property: Component 14, NdisMedium  = 0
[01]24D8.06B4::2026-11-11 23:53:27.322404600 [Microsoft-Windows-PktMon] Property: Component 14, IfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322405100 [Microsoft-Windows-PktMon] Drop Counters: Component 14, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322405600 [Microsoft-Windows-PktMon] Flow Counters: Component 14, Edge Lower, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322406200 [Microsoft-Windows-PktMon] Component 13, Type IPSec , Name tcpip.sys, IPSEC
[01]24D8.06B4::2026-11-11 23:53:27.322406700 [Microsoft-Windows-PktMon] Drop Counters: Component 13, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322407300 [Microsoft-Windows-PktMon] Component 12, Type 11, Name tcpip.sys, TCP/IPv6 - L3/L4
[01]24D8.06B4::2026-11-11 23:53:27.322407700 [Microsoft-Windows-PktMon] Property: Component 12, IP Address  = fe80::73d2:db5f:f7bd:6dc0
[01]24D8.06B4::2026-11-11 23:53:27.322408000 [Microsoft-Windows-PktMon] Property: Component 12, IP Address  = 2404:8000:1122:7c1:ffcf:5dbf:b248:3661
[01]24D8.06B4::2026-11-11 23:53:27.322408200 [Microsoft-Windows-PktMon] Property: Component 12, IP Address  = 2404:8000:1122:7c1:b95d:74ab:15ad:87df
[01]24D8.06B4::2026-11-11 23:53:27.322408600 [Microsoft-Windows-PktMon] Property: Component 12, Compartment ID  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322408800 [Microsoft-Windows-PktMon] Property: Component 12, IpIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322409600 [Microsoft-Windows-PktMon] Drop Counters: Component 12, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322410100 [Microsoft-Windows-PktMon] Component 11, Type 11, Name tcpip.sys, TCP/IPv6 - L3/L4
[01]24D8.06B4::2026-11-11 23:53:27.322410300 [Microsoft-Windows-PktMon] Property: Component 11, IP Address  = ::1
[01]24D8.06B4::2026-11-11 23:53:27.322410700 [Microsoft-Windows-PktMon] Property: Component 11, Compartment ID  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322411000 [Microsoft-Windows-PktMon] Property: Component 11, IpIfIndex  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322411400 [Microsoft-Windows-PktMon] Drop Counters: Component 11, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322411700 [Microsoft-Windows-PktMon] Component 10, Type 11, Name tcpip.sys, TCP/IPv4 - L3/L4
[01]24D8.06B4::2026-11-11 23:53:27.322412000 [Microsoft-Windows-PktMon] Property: Component 10, IP Address  = 192.168.18.14
[01]24D8.06B4::2026-11-11 23:53:27.322412400 [Microsoft-Windows-PktMon] Property: Component 10, Compartment ID  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322412700 [Microsoft-Windows-PktMon] Property: Component 10, IpIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322413300 [Microsoft-Windows-PktMon] Drop Counters: Component 10, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322413700 [Microsoft-Windows-PktMon] Component 9, Type 11, Name tcpip.sys, TCP/IPv4 - L3/L4
[01]24D8.06B4::2026-11-11 23:53:27.322413900 [Microsoft-Windows-PktMon] Property: Component 9, IP Address  = 127.0.0.1
[01]24D8.06B4::2026-11-11 23:53:27.322414200 [Microsoft-Windows-PktMon] Property: Component 9, Compartment ID  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322414400 [Microsoft-Windows-PktMon] Property: Component 9, IpIfIndex  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322414900 [Microsoft-Windows-PktMon] Drop Counters: Component 9, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322415400 [Microsoft-Windows-PktMon] Component 8, Type Protocol , Name tcpip.sys, TCP/IPv6 - L2
[01]24D8.06B4::2026-11-11 23:53:27.322415700 [Microsoft-Windows-PktMon] Property: Component 8, EtherType  = IPv6
[01]24D8.06B4::2026-11-11 23:53:27.322416300 [Microsoft-Windows-PktMon] Property: Component 8, Compartment ID  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322416500 [Microsoft-Windows-PktMon] Property: Component 8, IpIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322416700 [Microsoft-Windows-PktMon] Property: Component 8, MiniportIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322417300 [Microsoft-Windows-PktMon] Drop Counters: Component 8, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322417800 [Microsoft-Windows-PktMon] Flow Counters: Component 8, Edge Upper, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322418200 [Microsoft-Windows-PktMon] Component 7, Type Protocol , Name tcpip.sys, TCP/IPv4 - L2
[01]24D8.06B4::2026-11-11 23:53:27.322418400 [Microsoft-Windows-PktMon] Property: Component 7, EtherType  = ARP
[01]24D8.06B4::2026-11-11 23:53:27.322418800 [Microsoft-Windows-PktMon] Property: Component 7, EtherType  = IPv4
[01]24D8.06B4::2026-11-11 23:53:27.322419000 [Microsoft-Windows-PktMon] Property: Component 7, Compartment ID  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322419200 [Microsoft-Windows-PktMon] Property: Component 7, IpIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322419500 [Microsoft-Windows-PktMon] Property: Component 7, MiniportIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322420000 [Microsoft-Windows-PktMon] Drop Counters: Component 7, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322420500 [Microsoft-Windows-PktMon] Flow Counters: Component 7, Edge Upper, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322420800 [Microsoft-Windows-PktMon] Component 6, Type Protocol , Name tcpip.sys, TCPIP
[01]24D8.06B4::2026-11-11 23:53:27.322421300 [Microsoft-Windows-PktMon] Property: Component 6, EtherType  = ARP
[01]24D8.06B4::2026-11-11 23:53:27.322421600 [Microsoft-Windows-PktMon] Property: Component 6, EtherType  = IPv4
[01]24D8.06B4::2026-11-11 23:53:27.322421900 [Microsoft-Windows-PktMon] Property: Component 6, MiniportIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322422100 [Microsoft-Windows-PktMon] Property: Component 6, NdisObject  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322422400 [Microsoft-Windows-PktMon] Drop Counters: Component 6, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322423000 [Microsoft-Windows-PktMon] Flow Counters: Component 6, Edge Lower, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322423400 [Microsoft-Windows-PktMon] Component 5, Type Protocol , Name tcpip.sys, TCPIP6
[01]24D8.06B4::2026-11-11 23:53:27.322423700 [Microsoft-Windows-PktMon] Property: Component 5, EtherType  = IPv6
[01]24D8.06B4::2026-11-11 23:53:27.322423900 [Microsoft-Windows-PktMon] Property: Component 5, MiniportIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322424100 [Microsoft-Windows-PktMon] Property: Component 5, NdisObject  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322424600 [Microsoft-Windows-PktMon] Drop Counters: Component 5, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322425300 [Microsoft-Windows-PktMon] Flow Counters: Component 5, Edge Lower, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322440100 [Microsoft-Windows-PktMon] Component 4, Type Filter , Name wfplwfs.sys, WFP Native MAC Layer LightWeight Filter
[01]24D8.06B4::2026-11-11 23:53:27.322440500 [Microsoft-Windows-PktMon] Property: Component 4, MiniportIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322440800 [Microsoft-Windows-PktMon] Property: Component 4, IfIndex  = 16
[01]24D8.06B4::2026-11-11 23:53:27.322441000 [Microsoft-Windows-PktMon] Property: Component 4, NdisObject  = 1
[01]24D8.06B4::2026-11-11 23:53:27.322441500 [Microsoft-Windows-PktMon] Drop Counters: Component 4, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322442100 [Microsoft-Windows-PktMon] Flow Counters: Component 4, Edge Lower, Edge Id 2, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322442600 [Microsoft-Windows-PktMon] Flow Counters: Component 4, Edge Upper, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.322443100 [Microsoft-Windows-PktMon] Component 3, Type Filter , Name pacer.sys, QoS Packet Scheduler
[01]24D8.06B4::2026-11-11 23:53:27.322443400 [Microsoft-Windows-PktMon] Property: Component 3, LowerIfIndex  = 16
[01]24D8.06B4::2026-11-11 23:53:27.322443700 [Microsoft-Windows-PktMon] Property: Component 3, MiniportIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.322443900 [Microsoft-Windows-PktMon] Property: Component 3, IfIndex  = 17
[01]24D8.06B4::2026-11-11 23:53:27.324693600 [Microsoft-Windows-PktMon] Property: Component 3, NdisObject  = 1
[01]24D8.06B4::2026-11-11 23:53:27.324698100 [Microsoft-Windows-PktMon] Drop Counters: Component 3, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.324699400 [Microsoft-Windows-PktMon] Flow Counters: Component 3, Edge Lower, Edge Id 2, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.324700300 [Microsoft-Windows-PktMon] Flow Counters: Component 3, Edge Upper, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.324701600 [Microsoft-Windows-PktMon] Component 2, Type Filter , Name wfplwfs.sys, WFP 802.3 MAC Layer LightWeight Filter
[01]24D8.06B4::2026-11-11 23:53:27.324702200 [Microsoft-Windows-PktMon] Property: Component 2, OptDataPath  = 1
[01]24D8.06B4::2026-11-11 23:53:27.324702800 [Microsoft-Windows-PktMon] Property: Component 2, LowerIfIndex  = 17
[01]24D8.06B4::2026-11-11 23:53:27.324703000 [Microsoft-Windows-PktMon] Property: Component 2, MiniportIfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.324703200 [Microsoft-Windows-PktMon] Property: Component 2, IfIndex  = 18
[01]24D8.06B4::2026-11-11 23:53:27.324703500 [Microsoft-Windows-PktMon] Property: Component 2, NdisObject  = 1
[01]24D8.06B4::2026-11-11 23:53:27.324703900 [Microsoft-Windows-PktMon] Drop Counters: Component 2, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.324704400 [Microsoft-Windows-PktMon] Flow Counters: Component 2, Edge Lower, Edge Id 2, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.324705400 [Microsoft-Windows-PktMon] Flow Counters: Component 2, Edge Upper, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.324705900 [Microsoft-Windows-PktMon] Component 1, Type Miniport , Name netadaptercx.sys, Realtek PCIe GbE Family Controller
[01]24D8.06B4::2026-11-11 23:53:27.324706300 [Microsoft-Windows-PktMon] Property: Component 1, PhysAddress  = 0x2CF05D056CC7
[01]24D8.06B4::2026-11-11 23:53:27.324706500 [Microsoft-Windows-PktMon] Property: Component 1, NdisMedium  = 0
[01]24D8.06B4::2026-11-11 23:53:27.324706900 [Microsoft-Windows-PktMon] Property: Component 1, IfGuid  = {a82cff5c-3de2-4e11-b491-074dbb2356c6}
[01]24D8.06B4::2026-11-11 23:53:27.324707200 [Microsoft-Windows-PktMon] Property: Component 1, IfIndex  = 13
[01]24D8.06B4::2026-11-11 23:53:27.324707500 [Microsoft-Windows-PktMon] Property: Component 1, NdisObject  = 1
[01]24D8.06B4::2026-11-11 23:53:27.324708000 [Microsoft-Windows-PktMon] Drop Counters: Component 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
[01]24D8.06B4::2026-11-11 23:53:27.324708600 [Microsoft-Windows-PktMon] Flow Counters: Component 1, Edge Upper, Edge Id 1, Direction In = Rx , Packets In 0, Bytes In 0, Direction Out = Tx , Packets Out 0, Bytes Out 0
