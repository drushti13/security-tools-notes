# Security Tools Notes

Structured notes covering practical usage of core cybersecurity tools across reconnaissance, analysis, and exploitation phases.

## Nmap — Network Scanning & Enumeration

- Performs network discovery and port scanning  
- Identifies live hosts, open ports, and exposed services  
- Supports service/version detection and OS fingerprinting  
- Helps build a clear attack surface before further testing  
- Used during reconnaissance and enumeration phases  

**Focus Areas**
- Host discovery (`-sn`, `-Pn`)  
- Port scanning (`-p`, `-F`, `-p-`)  
- Service detection (`-sV`, `-A`)  
- Scan optimization (`-T4`, rate controls)  

## Wireshark — Network Traffic Analysis

- Packet-level inspection of network traffic  
- Captures and analyzes real-time communication  
- Provides deep visibility into protocols and sessions  
- Useful for detecting anomalies and debugging issues  

**Focus Areas**
- Packet structure and protocol breakdown  
- Identifying suspicious traffic patterns  
- DNS, HTTP, TCP analysis  
- Filtering and stream following  

## Burp Suite — Web Application Testing

- Intercepts and manipulates HTTP/HTTPS traffic  
- Analyzes request-response lifecycle  
- Identifies vulnerabilities in web applications  
- Core tool for manual web security testing  

**Focus Areas**
- Proxy interception and traffic analysis  
- Request manipulation  
- Authentication and session testing  
- Input validation testing  

### Burp Repeater — Manual Request Testing

- Sends and modifies HTTP requests manually  
- Allows controlled testing of parameters  
- Helps observe backend response behavior  

**Focus Areas**
- Parameter manipulation  
- Testing edge cases  
- Identifying logic flaws (e.g., IDOR, injection points)  

### Burp Intruder — Automated Input Testing

- Performs automated attacks using payload lists  
- Supports brute force and fuzzing techniques  
- Identifies weak input validation and authentication flaws  

**Focus Areas**
- Payload injection strategies  
- Brute force testing  
- Parameter fuzzing  
- Response comparison  

## Gobuster — Directory & DNS Enumeration

- Discovers hidden directories and files using wordlists  
- Performs DNS and virtual host enumeration  
- Expands attack surface during reconnaissance  

**Focus Areas**
- Directory brute forcing  
- Wordlist usage and tuning  
- Endpoint discovery  
- Enumeration strategy  

## Metasploit — Exploitation Framework

- Framework for developing and executing exploits  
- Provides modules for payloads, exploits, and auxiliary tasks  
- Used to validate and demonstrate real-world impact  

**Focus Areas**
- Exploit selection and configuration  
- Payload handling  
- Session management  
- Post-exploitation basics  

## Workflow Mapping

| Phase | Tools |
|------|------|
| Reconnaissance | Nmap, Gobuster |
| Enumeration | Nmap, Burp Suite |
| Analysis | Wireshark |
| Exploitation | Metasploit |
| Web Testing | Burp Suite (Repeater, Intruder) |

## Summary

- Covers practical usage across key cybersecurity phases  
- Focused on tool functionality and real-world application  
- Designed for quick revision and structured learning  
