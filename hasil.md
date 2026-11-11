PS C:\WINDOWS\system32> Write-Host "`n===== SERVER DATA YANG DITERIMA CLIENT ====="
>>
>> curl.exe -sk --http1.1 `
>>     --resolve www.growtopia1.com:443:127.0.0.1 `
>>     -H "Content-Type: application/x-www-form-urlencoded" `
>>     --data "version=5.61&protocol=227" `
>>     https://www.growtopia1.com/growtopia/server_data.php |
>>     Select-String '^(server|port|type|type2|loginurl|meta)\|'
>>
>> Write-Host "`n===== TCP LISTENERS ====="
>>
>> Get-NetTCPConnection -State Listen |
>>     Where-Object LocalPort -in 80,443,3000,8443 |
>>     Format-Table LocalAddress,LocalPort,OwningProcess -AutoSize
>>
>> Write-Host "`n===== GAME UDP LISTENER ====="
>>
>> Get-NetUDPEndpoint -LocalPort 17091 |
>>     Format-Table LocalAddress,LocalPort,OwningProcess -AutoSize

===== SERVER DATA YANG DITERIMA CLIENT =====

server|127.0.0.1
port|17091
type|1
type2|1
loginurl|www.growtopia1.com
meta|gurotopia

===== TCP LISTENERS =====



LocalAddress LocalPort OwningProcess
------------ --------- -------------
127.0.0.1         8443         13988
127.0.0.1         3000          9960
127.0.0.1          443          4720
127.0.0.1           80          4720



===== GAME UDP LISTENER =====

LocalAddress LocalPort OwningProcess
------------ --------- -------------
0.0.0.0          17091         13988


PS C:\WINDOWS\system32> Write-Host "`n===== RESET PAKET MONITOR ====="
>>
>> pktmon stop
>> pktmon filter remove
>>
>> Write-Host "`n===== PASANG FILTER PORT ====="
>>
>> pktmon filter add -p 80
>> pktmon filter add -p 443
>> pktmon filter add -p 3000
>> pktmon filter add -p 8443
>> pktmon filter add -p 17091
>>
>> pktmon filter list
>>
>> Write-Host "`n===== MULAI CAPTURE ====="
>>
>> pktmon start --capture --file-name C:\GTPS\GTPS-connection.etl

===== RESET PAKET MONITOR =====
Packet Monitor is not running.
Removed all filters.

===== PASANG FILTER PORT =====
Filter added.
Filter added.
Filter added.
Filter added.
Filter added.
Packet Filters:
     # Name     Port
     - ----     ----
     1 <empty>    80
     2 <empty>   443
     3 <empty>  3000
     4 <empty>  8443
     5 <empty> 17091

===== MULAI CAPTURE =====

Logger Parameters:
    Logger name:        PktMon
    Logging mode:       Circular
    Log file:           C:\GTPS\GTPS-connection.etl
    Max file size:      512 MB
    Memory used:        128 MB

Collected Data:
    Packet counters, packet capture

Capture Type:
    All packets

Monitored Components:
    All

Packet Filters:
     # Name     Port
     - ----     ----
     1 <empty>    80
     2 <empty>   443
     3 <empty>  3000
     4 <empty>  8443
     5 <empty> 17091
PS C:\WINDOWS\system32> Write-Host "`n===== PACKET COUNTERS ====="
>> pktmon counters
>>
>> Write-Host "`n===== STOP CAPTURE ====="
>> pktmon stop
>>
>> Write-Host "`n===== CONVERT CAPTURE ====="
>> pktmon etl2txt C:\GTPS\GTPS-connection.etl `
>>     --out C:\GTPS\GTPS-connection.txt `
>>     --brief
>>
>> Write-Host "`n===== FILTER KONEKSI GAME DAN DROP ====="
>> Select-String `
>>     -Path C:\GTPS\GTPS-connection.txt `
>>     -Pattern '17091|8443|3000|443|drop|Drop' |
>>     Select-Object -First 160

===== PACKET COUNTERS =====

NIC: Realtek PCIe GbE Family Controller
 Id Name                       Counter  Direction     Packets          Bytes | Direction     Packets          Bytes
 -- ----                       -------  ---------     -------          ----- | ---------     -------          -----
 14 Realtek PCIe GbE Family... Lower    Rx             26.198     30.793.257 | Tx              4.598        848.570
  1 Realtek PCIe GbE Family... Upper    Rx             43.700     51.697.272 | Tx              4.250        685.032
                                                                             |
  4 WFP Native Filter          Lower    Rx             43.700     51.697.272 | Tx              4.244        684.588
                               Upper    Rx             43.700     51.697.272 | Tx              4.244        684.588
  3 QoS Packet Scheduler       Lower    Rx                  0              0 | Tx              4.244        684.588
                               Upper    Rx                  0              0 | Tx              4.244        684.588
                                                                             |
  5 TCPIP6                     Lower    Rx             43.668     51.682.872 | Tx              4.229        683.095
  6 TCPIP                      Lower    Rx                 32         14.400 | Tx                 15          1.493


===== STOP CAPTURE =====
Flushing logs...
Merging metadata...
Log file: C:\GTPS\GTPS-connection.etl (No events lost)

===== CONVERT CAPTURE =====
Processing...

Events formatted:    161206
Formatted file:      C:\GTPS\GTPS-connection.txt

===== FILTER KONEKSI GAME DAN DROP =====

C:\GTPS\GTPS-connection.txt:5:  2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 97: 2404:8000:1122:7c1:b95d:74ab:15a
d:87df.55645 > 2404:8000:12:14::e.443: UDP, length 35
C:\GTPS\GTPS-connection.txt:7:  2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 97: 2404:8000:1122:7c1:b95d:74ab:15a
d:87df.55645 > 2404:8000:12:14::e.443: UDP, length 35
C:\GTPS\GTPS-connection.txt:9:  2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 97: 2404:8000:1122:7c1:b95d:74ab:15a
d:87df.55645 > 2404:8000:12:14::e.443: UDP, length 35
C:\GTPS\GTPS-connection.txt:11: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 97: 2404:8000:1122:7c1:b95d:74ab:15
ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 35
C:\GTPS\GTPS-connection.txt:13: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 97: 2404:8000:1122:7c1:b95d:74ab:15
ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 35
C:\GTPS\GTPS-connection.txt:15: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 97: 2404:8000:1122:7c1:b95d:74ab:15
ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 35
C:\GTPS\GTPS-connection.txt:17: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 97: 2404:8000:1122:7c1:b95d:74ab:15
ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 35
C:\GTPS\GTPS-connection.txt:19: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 310: 2404:8000:12:14::e.443 > 2404:
8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 248
C:\GTPS\GTPS-connection.txt:21: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 310: 2404:8000:12:14::e.443 > 2404:
8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 248
C:\GTPS\GTPS-connection.txt:23: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 310: 2404:8000:12:14::e.443 > 2404:
8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 248
C:\GTPS\GTPS-connection.txt:25: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 310: 2404:8000:12:14::e.443 > 2404:
8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 248
C:\GTPS\GTPS-connection.txt:27: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 310: 2404:8000:12:14::e.443 > 2404:
8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 248
C:\GTPS\GTPS-connection.txt:29: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 93: 2404:8000:12:14::e.443 > 2404:8
000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 31
C:\GTPS\GTPS-connection.txt:31: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 88: 2404:8000:12:14::e.443 > 2404:8
000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 26
C:\GTPS\GTPS-connection.txt:33: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 93: 2404:8000:12:14::e.443 > 2404:8
000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 31
C:\GTPS\GTPS-connection.txt:35: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 88: 2404:8000:12:14::e.443 > 2404:8
000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 26
C:\GTPS\GTPS-connection.txt:37: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 93: 2404:8000:12:14::e.443 > 2404:8
000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 31
C:\GTPS\GTPS-connection.txt:39: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 88: 2404:8000:12:14::e.443 > 2404:8
000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 26
C:\GTPS\GTPS-connection.txt:41: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 93: 2404:8000:12:14::e.443 > 2404:8
000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 31
C:\GTPS\GTPS-connection.txt:43: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 88: 2404:8000:12:14::e.443 > 2404:8
000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 26
C:\GTPS\GTPS-connection.txt:45: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 93: 2404:8000:12:14::e.443 > 2404:8
000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 31
C:\GTPS\GTPS-connection.txt:47: 30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 88: 2404:8000:12:14::e.443 > 2404:8
000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 26
C:\GTPS\GTPS-connection.txt:49: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:15
ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:51: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:15
ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:53: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:15
ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:55: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:15
ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:57: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:15
ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:59: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:15
ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:61: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:15
ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:63: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1083: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1021
C:\GTPS\GTPS-connection.txt:65: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1083: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1021
C:\GTPS\GTPS-connection.txt:67: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1083: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1021
C:\GTPS\GTPS-connection.txt:69: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1083: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1021
C:\GTPS\GTPS-connection.txt:71: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1083: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1021
C:\GTPS\GTPS-connection.txt:73: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1083: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1021
C:\GTPS\GTPS-connection.txt:75: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1083: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1021
C:\GTPS\GTPS-connection.txt:77: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1287: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1225
C:\GTPS\GTPS-connection.txt:79: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1287: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1225
C:\GTPS\GTPS-connection.txt:81: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1287: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1225
C:\GTPS\GTPS-connection.txt:83: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1287: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1225
C:\GTPS\GTPS-connection.txt:85: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1287: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1225
C:\GTPS\GTPS-connection.txt:87: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1287: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1225
C:\GTPS\GTPS-connection.txt:89: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1287: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 1225
C:\GTPS\GTPS-connection.txt:91: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 552: 2404:8000:1122:7c1:b95d:74ab:1
5ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 490
C:\GTPS\GTPS-connection.txt:93: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 552: 2404:8000:1122:7c1:b95d:74ab:1
5ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 490
C:\GTPS\GTPS-connection.txt:95: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 552: 2404:8000:1122:7c1:b95d:74ab:1
5ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 490
C:\GTPS\GTPS-connection.txt:97: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 552: 2404:8000:1122:7c1:b95d:74ab:1
5ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 490
C:\GTPS\GTPS-connection.txt:99: 2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 552: 2404:8000:1122:7c1:b95d:74ab:1
5ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 490
C:\GTPS\GTPS-connection.txt:101:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 552: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 490
C:\GTPS\GTPS-connection.txt:103:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 552: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 490
C:\GTPS\GTPS-connection.txt:105:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 204: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 142
C:\GTPS\GTPS-connection.txt:107:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 204: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 142
C:\GTPS\GTPS-connection.txt:109:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 204: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 142
C:\GTPS\GTPS-connection.txt:111:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 204: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 142
C:\GTPS\GTPS-connection.txt:113:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 204: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 142
C:\GTPS\GTPS-connection.txt:115:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 104: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 42
C:\GTPS\GTPS-connection.txt:117:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 104: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 42
C:\GTPS\GTPS-connection.txt:119:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 104: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 42
C:\GTPS\GTPS-connection.txt:121:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 104: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 42
C:\GTPS\GTPS-connection.txt:123:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 104: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 42
C:\GTPS\GTPS-connection.txt:125:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 104: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 42
C:\GTPS\GTPS-connection.txt:127:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 104: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 42
C:\GTPS\GTPS-connection.txt:129:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 88: 2404:8000:12:14::e.443 > 2404:
8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 26
C:\GTPS\GTPS-connection.txt:131:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 88: 2404:8000:12:14::e.443 > 2404:
8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 26
C:\GTPS\GTPS-connection.txt:133:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 88: 2404:8000:12:14::e.443 > 2404:
8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 26
C:\GTPS\GTPS-connection.txt:135:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 88: 2404:8000:12:14::e.443 > 2404:
8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 26
C:\GTPS\GTPS-connection.txt:137:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 88: 2404:8000:12:14::e.443 > 2404:
8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 26
C:\GTPS\GTPS-connection.txt:139:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 408: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 346
C:\GTPS\GTPS-connection.txt:141:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 408: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 346
C:\GTPS\GTPS-connection.txt:143:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 408: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 346
C:\GTPS\GTPS-connection.txt:145:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 408: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 346
C:\GTPS\GTPS-connection.txt:147:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 408: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 346
C:\GTPS\GTPS-connection.txt:149:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 408: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 346
C:\GTPS\GTPS-connection.txt:151:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 408: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 346
C:\GTPS\GTPS-connection.txt:153:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1286: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1224
C:\GTPS\GTPS-connection.txt:155:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1286: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1224
C:\GTPS\GTPS-connection.txt:157:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1286: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1224
C:\GTPS\GTPS-connection.txt:159:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1286: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1224
C:\GTPS\GTPS-connection.txt:161:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1286: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1224
C:\GTPS\GTPS-connection.txt:163:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1286: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1224
C:\GTPS\GTPS-connection.txt:165:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1286: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1224
C:\GTPS\GTPS-connection.txt:167:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1292: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1230
C:\GTPS\GTPS-connection.txt:169:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1292: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1230
C:\GTPS\GTPS-connection.txt:171:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1292: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1230
C:\GTPS\GTPS-connection.txt:173:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1292: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1230
C:\GTPS\GTPS-connection.txt:175:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1292: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1230
C:\GTPS\GTPS-connection.txt:177:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1292: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1230
C:\GTPS\GTPS-connection.txt:179:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 1292: 2404:8000:1122:7c1:b95d:74ab
:15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 1230
C:\GTPS\GTPS-connection.txt:181:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 937: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 875
C:\GTPS\GTPS-connection.txt:183:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 937: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 875
C:\GTPS\GTPS-connection.txt:185:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 937: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 875
C:\GTPS\GTPS-connection.txt:187:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 937: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 875
C:\GTPS\GTPS-connection.txt:189:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 937: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 875
C:\GTPS\GTPS-connection.txt:191:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 937: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 875
C:\GTPS\GTPS-connection.txt:193:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 937: 2404:8000:1122:7c1:b95d:74ab:
15ad:87df.61838 > 2001:4860:482a:400::.443: UDP, length 875
C:\GTPS\GTPS-connection.txt:195:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 149: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 87
C:\GTPS\GTPS-connection.txt:197:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 143: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 81
C:\GTPS\GTPS-connection.txt:199:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 149: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 87
C:\GTPS\GTPS-connection.txt:201:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 143: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 81
C:\GTPS\GTPS-connection.txt:203:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 149: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 87
C:\GTPS\GTPS-connection.txt:205:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 143: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 81
C:\GTPS\GTPS-connection.txt:207:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 149: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 87
C:\GTPS\GTPS-connection.txt:209:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 143: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 81
C:\GTPS\GTPS-connection.txt:211:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 149: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 87
C:\GTPS\GTPS-connection.txt:213:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 143: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 81
C:\GTPS\GTPS-connection.txt:215:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 259: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 197
C:\GTPS\GTPS-connection.txt:217:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 259: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 197
C:\GTPS\GTPS-connection.txt:219:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 259: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 197
C:\GTPS\GTPS-connection.txt:221:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 259: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 197
C:\GTPS\GTPS-connection.txt:223:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 259: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 197
C:\GTPS\GTPS-connection.txt:225:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 124: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 62
C:\GTPS\GTPS-connection.txt:227:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 124: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 62
C:\GTPS\GTPS-connection.txt:229:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 124: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 62
C:\GTPS\GTPS-connection.txt:231:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 124: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 62
C:\GTPS\GTPS-connection.txt:233:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 124: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 62
C:\GTPS\GTPS-connection.txt:235:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 168: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 106
C:\GTPS\GTPS-connection.txt:236:[02]0004.0288::2026-11-11 23:35:01.931203000 [Microsoft-Windows-PktMon] PktGroupId 5629
49953421356, PktNumber 1, Appearance 0, Direction Rx , Type Ethernet , Component 1, Edge 1, Filter 2, OriginalSize 168,
 LoggedSize 128
C:\GTPS\GTPS-connection.txt:237:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 168: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 106
C:\GTPS\GTPS-connection.txt:239:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 168: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 106
C:\GTPS\GTPS-connection.txt:241:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 168: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 106
C:\GTPS\GTPS-connection.txt:243:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 168: 2404:8000:12:14::e.443 > 2404
:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 106
C:\GTPS\GTPS-connection.txt:245:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1286: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1224
C:\GTPS\GTPS-connection.txt:247:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1286: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1224
C:\GTPS\GTPS-connection.txt:249:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1286: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1224
C:\GTPS\GTPS-connection.txt:251:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1286: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1224
C:\GTPS\GTPS-connection.txt:253:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1286: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1224
C:\GTPS\GTPS-connection.txt:255:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:257:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:259:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:261:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:263:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:265:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:267:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:269:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:271:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:273:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:275:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:277:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:279:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:281:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:283:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:285:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:287:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:289:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:291:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:293:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:295:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:1
5ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:297:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:1
5ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:299:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:1
5ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:301:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:1
5ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:303:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:1
5ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:305:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:1
5ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:307:        2C-F0-5D-05-6C-C7 > 30-49-9E-4B-0D-0A, IPv6, length 96: 2404:8000:1122:7c1:b95d:74ab:1
5ad:87df.55645 > 2404:8000:12:14::e.443: UDP, length 34
C:\GTPS\GTPS-connection.txt:309:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:311:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:313:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:315:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:317:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:319:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
C:\GTPS\GTPS-connection.txt:321:        30-49-9E-4B-0D-0A > 2C-F0-5D-05-6C-C7, IPv6, length 1292: 2404:8000:12:14::e.443 > 240
4:8000:1122:7c1:b95d:74ab:15ad:87df.55645: UDP, length 1230
