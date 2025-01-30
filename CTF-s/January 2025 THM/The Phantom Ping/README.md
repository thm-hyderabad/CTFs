# The Phantom Ping

## Category
**Network Analysis**

## Description
A notorious hacker group, The Phantoms, has launched a covert attack on QuantumCorp, leaving behind a suspicious network capture file (THMwireshark.pcapng). Hidden within the file lies a secret message and their signature flag.

## Solution

The `.pcapng` file contains data packets which uses multple protocols.


### Steps to Solve:

1. **Filter Protocols in Wireshark**:
Open the .pcapng file in Wireshark and apply filters to isolate relevant traffic:

HTTP: http
DNS: dns
FTP: ftp
Noise: Ignore icmp (ping) packets if you see any of those packets.

2. **Extract Flag Parts**:
   
---> Part 1: HTTP GET Request
     Search for HTTP GET requests in wireshark 
     http.request.method == "GET"  
     Locate the request to http://example.com/?flag=THM10{Pcap.
Flag Part 1: THM10{Pcap


---> Part 2: DNS Query
     Filter DNS queries in wireshark
     dns.qry.name contains "flag"  
     Identify the DNS query with _extraction_.domain.local .
Flag Part 2: _extraction_


---> Part 3: FTP File Transfer
     Filter FTP traffic after dealing with http and dns traffic in wireshark
     Follow the FTP data stream to find an uploaded file (flag.txt) containing 'master}'.
Flag Part 3: master}

3. **Reconstruct the Full Flag**:
   Combine the parts in order to get desired flag (i.e THM10{Pcap_extraction_master}).



