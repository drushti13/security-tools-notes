
`tcpdump` is a command-line packet analyzer used to capture and inspect network traffic in real time or from `.pcap` files.
-i	Select interface
-w	Write to file
-r	Read from file
-c	Limit packet count
-n	Disable DNS resolution
-nn	Disable DNS and port resolution
-v	Increase verbosity

## Basic Commands

| Description | Command |
|------------|--------|
| Capture packets on interface eth0 | `tcpdump -i eth0` |
| Capture packets on all interfaces | `tcpdump -i any` |
| Capture packets on eth0 and save to capture.pcap | `tcpdump -i eth0 -w capture.pcap` |
| Read and display packets from a .pcap file | `tcpdump -r capture.pcap` |
| Capture only 10 packets from eth0 and stop | `tcpdump -i eth0 -c 10` |

## Output Control

| Description | Command |
|------------|--------|
| Disable DNS resolution (show IP addresses only) | `tcpdump -n` |
| Disable DNS and port resolution (show raw IPs and ports) | `tcpdump -nn` |
| Display slightly more packet details | `tcpdump -v` |
| Display more detailed packet information | `tcpdump -vv` |
| Display maximum verbosity for packet details | `tcpdump -vvv` |

## Interface Management

| Description | Command |
|------------|--------|
| List all network interfaces | `ip a` |
| Capture packets on eth0 | `tcpdump -i eth0` |
| Capture packets on all interfaces | `tcpdump -i any` |

## File Operations

| Description | Command |
|------------|--------|
| Capture traffic and write to file.pcap | `tcpdump -i eth0 -w file.pcap` |
| Read packets from file.pcap | `tcpdump -r file.pcap` |
| Read first 5 packets from file without name resolution | `tcpdump -r file.pcap -c 5 -n` |
| Count total packets in the file | `tcpdump -r file.pcap \| wc -l` |

## Host Filtering

| Description | Command |
|------------|--------|
| Capture packets to/from IP 1.1.1.1 | `tcpdump host 1.1.1.1` |
| Capture packets to/from example.com | `tcpdump host example.com` |
| Capture packets only from source IP | `tcpdump src host 1.1.1.1` |
| Capture packets only to destination IP | `tcpdump dst host 1.1.1.1` |

## Port Filtering

| Description | Command |
|------------|--------|
| Capture packets on port 80 (HTTP) | `tcpdump port 80` |
| Capture packets on port 53 (DNS) | `tcpdump port 53` |
| Capture packets from source port 443 | `tcpdump src port 443` |
| Capture packets to destination port 22 (SSH) | `tcpdump dst port 22` |

## Protocol Filtering

| Description | Command |
|------------|--------|
| Capture TCP packets only | `tcpdump tcp` |
| Capture UDP packets only | `tcpdump udp` |
| Capture ICMP packets | `tcpdump icmp` |
| Capture IPv4 packets | `tcpdump ip` |
| Capture IPv6 packets | `tcpdump ip6` |

---

## Logical Operators

| Description | Command |
|------------|--------|
| Capture TCP traffic involving specific host | `tcpdump host 1.1.1.1 and tcp` |
| Capture UDP or ICMP packets | `tcpdump udp or icmp` |
| Capture all packets except TCP | `tcpdump not tcp` |

## Combined Filters

| Description | Command |
|------------|--------|
| Capture SSH traffic on all interfaces | `tcpdump -i any tcp port 22` |
| Capture DNS traffic on eth0 without name resolution | `tcpdump -i eth0 port 53 -n` |
| Capture HTTPS traffic for example.com and save to file | `tcpdump -i eth0 host example.com and tcp port 443 -w https.pcap` |
| Capture NTP traffic on WiFi interface | `tcpdump -i wlan0 udp port 123` |

## Practical Usage

| Description | Command |
|------------|--------|
| Capture and save traffic for later analysis | `tcpdump -i eth0 -w capture.pcap` |
| Analyze saved traffic without DNS resolution | `tcpdump -r capture.pcap -n` |
| Filter ICMP packets from saved capture | `tcpdump -r capture.pcap icmp` |


