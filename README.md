# Security Tools Notes

A collection of my notes on cybersecurity tools that I've learned through TryHackMe, PortSwigger Web Security Academy, and CTFs. This repository focuses on the practical usage of each tool, including common commands, real-world use cases, and what I learned while using them.

## Contents

### Reconnaissance & Content Discovery

- **Nmap** (`nmap.md`)
  - Host discovery
  - Port scanning
  - Service and OS detection
  - NSE scripts

- **Google Dorking** (`google-dorking.md`)
  - Advanced Google search operators
  - Reverse image searching with Yandex and Google Lens
  - Website history using Wayback Machine
  - Technology fingerprinting with Wappalyzer

- **Content Discovery Tools** (`content-discovery-tools.md`)
  - Gobuster
  - ffuf
  - dirsearch
  - Directory and file enumeration
  - Virtual host discovery

### Password Cracking

- **John the Ripper** (`john-the-ripper.md`)
  - Hash identification
  - Password cracking
  - Custom rules
  - Cracking ZIP, RAR, and SSH private keys

- **Hashcat** (`hashcat.md`)
  - Dictionary attacks
  - Hash modes
  - Attack modes
  - Password recovery using wordlists

### Web Application Security

- **Burp Suite** (`burp-suite.md`)
  - Proxy for intercepting HTTP/HTTPS requests
  - Repeater for modifying and replaying requests
  - Intruder for brute-force attacks and fuzzing
  - Decoder for encoding and decoding data
  - Comparer for comparing requests and responses
  - Sequencer for analyzing session token randomness
  - Target and Site Map for application mapping
  - Authentication testing
  - Request manipulation and vulnerability testing
 
### Network Analysis

- **Wireshark** (`wireshark.md`)
  - Packet capture and analysis
  - Protocol inspection
  - Network troubleshooting

- **tcpdump** (`tcpdump.md`)
  - Command-line packet capture
  - Traffic filtering
  - PCAP analysis

## Repository Goal

I'm building this repository as I learn new cybersecurity tools through hands-on labs and CTFs. The goal is to keep practical notes that I can revisit while also documenting my learning journey.

More tools and notes will be added as I continue learning.
