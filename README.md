# Security Tools Notes

This repository contains notes and command examples for commonly used cybersecurity tools.

These tools are widely used for penetration testing, network analysis, and vulnerability assessment.


## Nmap

Nmap is a network scanning tool used to discover hosts and services on a network.

Basic scan

nmap 10.10.10.10

Service detection

nmap -sV 10.10.10.10

Aggressive scan

nmap -A 10.10.10.10

Use case:
Identifying open ports and services.


## Wireshark

Wireshark is a network protocol analyzer used to inspect network traffic.

Common uses:

- Analyzing packets
- Detecting suspicious traffic
- Troubleshooting network problems


## Burp Suite

Burp Suite is used for web application security testing.

Capabilities include:

- Intercepting HTTP requests
- Testing for vulnerabilities
- Modifying web requests

### Burp Repeater

Burp Repeater allows testers to **manually modify and resend HTTP requests** to observe how a server responds.

Example:

GET /profile?id=5

Modified request:

GET /profile?id=10

Use case:
Testing parameter manipulation and vulnerabilities such as IDOR or SQL injection.

---

### Burp Intruder

Burp Intruder is used for **automated attacks on web application parameters** using payload lists.

Common uses:
- Brute force attacks
- Parameter fuzzing
- Testing input validation

Example payload list:

123456  
password  
admin  
qwerty

Intruder sends multiple requests with different payloads to identify vulnerabilities.

## Gobuster

Gobuster is used for directory and DNS brute forcing.

Example:

gobuster dir -u http://example.com -w /usr/share/wordlists/dirb/common.txt

Use case:
Finding hidden directories on websites.


## Metasploit

Metasploit is a penetration testing framework used to develop and execute exploits.

Example workflow:

1. Search for exploit
2. Configure payload
3. Launch exploit

Use case:
Testing vulnerabilities in controlled environments.

