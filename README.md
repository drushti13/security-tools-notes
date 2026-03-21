# Security Tools Notes

This repository contains theoretical notes for commonly used cybersecurity tools.

These tools are used in penetration testing, network analysis, and vulnerability assessment.

## Nmap

Nmap is a network discovery and security auditing tool.

### Why it is used
- To identify active hosts on a network  
- To detect open ports and running services  
- To gather information about target systems  

### What it does
- Scans networks to find live systems  
- Identifies open, closed, and filtered ports  
- Detects service versions and operating systems  

### How it helps
- Provides a clear attack surface of a target  
- Helps in planning further exploitation  
- Assists in network inventory and monitoring  

### When to use
- During reconnaissance phase of penetration testing  
- Before vulnerability assessment  
- When mapping a network environment  

## Wireshark

Wireshark is a network protocol analyzer.

### Why it is used
- To inspect and analyze network traffic  
- To understand communication between systems  

### What it does
- Captures packets in real time  
- Displays detailed protocol-level information  

### How it helps
- Identifies suspicious or malicious traffic  
- Helps troubleshoot network issues  
- Provides deep visibility into packet behavior  

### When to use
- During network troubleshooting  
- When analyzing suspicious traffic  
- While learning protocol behavior  

## Burp Suite

Burp Suite is a web application security testing tool.

### Why it is used
- To test web applications for vulnerabilities  
- To intercept and manipulate HTTP requests  

### What it does
- Acts as a proxy between browser and server  
- Allows inspection and modification of requests and responses  

### How it helps
- Identifies security flaws in web applications  
- Enables manual and automated testing  

### When to use
- During web application penetration testing  
- When analyzing application behavior  
- While testing authentication and input validation  

### Burp Repeater

Burp Repeater is a module within Burp Suite for manual request testing.

### Why it is used
- To test how a server responds to modified requests  

### What it does
- Allows resending and modifying HTTP requests multiple times  

### How it helps
- Helps identify vulnerabilities like IDOR, SQL injection  
- Enables precise testing of parameters  

### When to use
- After intercepting a request  
- When testing specific inputs manually  
- During detailed vulnerability analysis  


### Burp Intruder

Burp Intruder is used for automated attacks on web application inputs.

### Why it is used
- To perform automated testing with multiple payloads  

### What it does
- Sends multiple requests with different payload combinations  

### How it helps
- Identifies weak authentication mechanisms  
- Discovers input validation flaws  

### When to use
- During brute force testing  
- When fuzzing parameters  
- While testing login forms and APIs  

## Gobuster

Gobuster is a tool for directory and DNS brute forcing.

### Why it is used
- To discover hidden files and directories  

### What it does
- Uses wordlists to brute-force endpoints  

### How it helps
- Finds hidden resources not visible in UI  
- Expands attack surface  

### When to use
- During web reconnaissance  
- Before vulnerability testing  
- When mapping web application structure  

## Metasploit

Metasploit is a penetration testing framework.

### Why it is used
- To develop and execute exploits  

### What it does
- Provides modules for exploits, payloads, and auxiliary functions  

### How it helps
- Validates vulnerabilities  
- Automates exploitation process  

### When to use
- After identifying vulnerabilities  
- During exploitation phase  
- In controlled penetration testing environments  

---
