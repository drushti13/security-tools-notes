
Nmap (Network Mapper) is a network discovery and security auditing tool used to identify hosts, services, open ports, and operating systems on a network.

## Target Specification

| Description | Command |
|------------|--------|
| Scan IP range using `-` | `nmap 192.168.0.1-10` |
| Scan subnet using `/` | `nmap 192.168.0.1/24` |
| Scan using hostname | `nmap example.com` |

## Host Discovery

| Description | Command |
|------------|--------|
| Discover live hosts only (ping scan) | `nmap -sn 192.168.0.1/24` |
| TCP SYN discovery | `nmap -PS 192.168.0.1/24` |
| TCP ACK discovery | `nmap -PA 192.168.0.1/24` |
| UDP discovery | `nmap -PU 192.168.0.1/24` |
| Treat all hosts as online | `nmap -Pn 192.168.0.1/24` |

## List Scan

| Description | Command |
|------------|--------|
| List targets without scanning | `nmap -sL 192.168.0.1/24` |

## Port Scanning

| Description | Command |
|------------|--------|
| Default scan (top 1000 ports) | `nmap 192.168.1.1` |
| Fast scan (top 100 ports) | `nmap -F 192.168.1.1` |
| Scan specific port range | `nmap -p10-1024 192.168.1.1` |
| Scan ports 1–25 | `nmap -p1-25 192.168.1.1` |
| Scan all ports (1–65535) | `nmap -p- 192.168.1.1` |
| Scan well-known ports | `nmap -p1-1023 192.168.1.1` |

## Scan Types

| Description | Command |
|------------|--------|
| TCP connect scan (full handshake) | `nmap -sT 192.168.1.1` |
| TCP SYN scan (half-open) | `nmap -sS 192.168.1.1` |
| UDP scan | `nmap -sU 192.168.1.1` |

## Service & OS Detection

| Description | Command |
|------------|--------|
| OS detection | `nmap -O 192.168.1.1` |
| Service and version detection | `nmap -sV 192.168.1.1` |
| Aggressive scan (OS + version + scripts + traceroute) | `nmap -A 192.168.1.1` |

## Timing & Performance

| Description | Command |
|------------|--------|
| Paranoid timing | `nmap -T0 192.168.1.1` |
| Sneaky timing | `nmap -T1 192.168.1.1` |
| Polite timing | `nmap -T2 192.168.1.1` |
| Normal timing (default) | `nmap -T3 192.168.1.1` |
| Aggressive timing | `nmap -T4 192.168.1.1` |
| Insane timing | `nmap -T5 192.168.1.1` |
| Set minimum parallel probes | `nmap --min-parallelism 10 192.168.1.1` |
| Set maximum parallel probes | `nmap --max-parallelism 100 192.168.1.1` |
| Set minimum packet rate | `nmap --min-rate 100 192.168.1.1` |
| Set maximum packet rate | `nmap --max-rate 1000 192.168.1.1` |
| Set host timeout | `nmap --host-timeout 30s 192.168.1.1` |

## Filtering & Combination

| Description | Command |
|------------|--------|
| Scan specific port on host | `nmap -p 80 192.168.1.1` |
| Scan multiple ports | `nmap -p 22,80,443 192.168.1.1` |
| Combine scan type and ports | `nmap -sS -p- 192.168.1.1` |

## Output & Debugging

| Description | Command |
|------------|--------|
| Increase verbosity | `nmap -v 192.168.1.1` |
| More verbose output | `nmap -vv 192.168.1.1` |
| Set verbosity level | `nmap -v4 192.168.1.1` |
| Enable debugging | `nmap -d 192.168.1.1` |
| Maximum debugging level | `nmap -d9 192.168.1.1` |


## Saving Scan Reports

| Description | Command |
|------------|--------|
| Save normal output | `nmap -oN scan.txt 192.168.1.1` |
| Save XML output | `nmap -oX scan.xml 192.168.1.1` |
| Save grepable output | `nmap -oG scan.gnmap 192.168.1.1` |
| Save all formats | `nmap -oA scan 192.168.1.1` |


## Practical Usage

| Description | Command |
|------------|--------|
| Discover live hosts | `nmap -sn 192.168.1.0/24` |
| Full aggressive scan | `nmap -A 192.168.1.1` |
| Fast scan common ports | `nmap -F 192.168.1.1` |
| Full port scan with SYN | `nmap -sS -p- 192.168.1.1` |
| Skip host discovery and scan | `nmap -Pn -p- 192.168.1.1` |


## Notes

- Default scan checks top 1000 ports  
- `-sn` only discovers hosts, not services  
- `-sL` lists targets without scanning  
- `-p-` scans all 65535 ports  
- `-A` is noisy and easily detectable  
- `-Pn` is useful when ICMP is blocked  
- `-T4` is commonly used for faster scans  
- `-oA` saves output in all formats  
- ping : utilizes a single protocol (ICMP) to determine if a host is reachable, Nmap utilizes a variety of TCP, UDP, and ICMP probes to determine the functional state (Open, Closed, or Filtered) of thousands of individual communication ports.
- Telnet is limited to testing one port at a time via manual user input. Nmap is a highly automated engine capable of scanning the entire theoretical range of $65,535$ TCP and UDP ports across multiple subnets simultaneously.
