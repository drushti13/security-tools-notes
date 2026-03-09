# Wireshark – Practical Notes

Wireshark is a network packet analyzer used for inspecting, filtering, and analyzing network traffic. It is widely used in cybersecurity for **packet analysis, network troubleshooting, and PCAP investigations**.

# Interface Components

## 1. Packet List Pane
Displays all captured packets in chronological order.

**What you do here**
- View packet number, time, source IP, destination IP, protocol, and packet length
- Quickly identify traffic types (HTTP, DNS, TCP, ICMP)
- Select packets to inspect their detailed information

**Things to check**
- Unusual source or destination IP addresses
- Suspicious protocols or ports
- Repeated packets indicating scanning or abnormal activity

## 2. Packet Details Pane
Displays a structured breakdown of the selected packet.

**What you do here**
- Expand protocol layers to inspect packet information

Protocol layers example:
Ethernet → IP → TCP/UDP → Application Layer

**Important fields to inspect**
- Source IP address
- Destination IP address
- Source and destination ports
- TCP flags (SYN, ACK, FIN)
- HTTP request or DNS query information

## 3. Packet Bytes Pane
Displays raw packet data in **hexadecimal and ASCII format**.

**What you do here**
- Inspect raw packet content
- Identify readable strings inside packet payload
- Detect encoded or hidden data

**Things to look for**
password
login
admin
token
flag


# Important Wireshark Actions

## Follow TCP Stream
Reconstructs the entire communication between two hosts.

**Steps**
1. Right-click a packet
2. Select **Follow**
3. Choose **TCP Stream**

**Used for**
- Viewing full HTTP requests and responses
- Extracting credentials
- Reconstructing conversations between client and server

## Searching Inside Packets
Shortcut: Ctrl + F
Recommended settings:
- Find By → String
- Search In → Packet Bytes


# Useful Display Filters

Display filters help isolate specific traffic in large packet captures.

**Filter by IP**

ip.addr == 192.168.1.10

**Filter by port**

tcp.port == 80

**Search for text inside packets**

frame contains "password"
frame contains "flag"

# Extract Files from Network Traffic

Wireshark can extract files transferred over certain protocols.

**Steps**
1. Go to **File → Export Objects**
2. Select protocol (HTTP, SMB, etc.)
3. Save the extracted files

**Used for**
- Recovering downloaded files
- Extracting images or documents
- Malware analysis

# Key Skills Practiced with Wireshark

- Packet Analysis  
- Network Traffic Analysis  
- Protocol Inspection  
- PCAP Investigation  
- Credential Detection in Traffic  
- Network Forensics

