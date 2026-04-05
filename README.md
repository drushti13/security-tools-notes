# Security Tools Notes

Structured notes covering the **practical usage of core cybersecurity tools** across reconnaissance, analysis, and exploitation phases.


## Reconnaissance & Enumeration

### **Nmap — Network Scanning & Enumeration**

* Performs network discovery and port scanning
* Identifies live hosts, open ports, and exposed services
* Supports service/version detection and OS fingerprinting
* Helps define the attack surface before further testing

**Focus Areas**

* Host discovery (`-sn`, `-Pn`)
* Port scanning (`-p`, `-F`, `-p-`)
* Service detection (`-sV`, `-A`)
* Scan optimization (`-T4`, rate controls)


### **Gobuster — Directory & DNS Enumeration**

* Discovers hidden directories and files using wordlists
* Performs DNS and virtual host enumeration
* Expands attack surface during reconnaissance

**Focus Areas**

* Directory brute forcing
* Wordlist usage and tuning
* Endpoint discovery
* Enumeration strate

### **DNSDumpster — Passive DNS Reconnaissance**

* Maps DNS records and infrastructure
* Identifies subdomains and related hosts
* Visualizes network relationships

**Focus Areas**

* Subdomain discovery
* DNS record analysis (A, MX, NS, TXT)
* Infrastructure mapping


### **Shodan — Internet-Wide Reconnaissance**

* Search engine for internet-connected devices
* Identifies exposed services, ports, and banners
* Provides geographic and service-level insights

**Focus Areas**

* Service/banner analysis
* Port-based searches
* Exposure assessment
* OSINT-based reconnaissance


## Network Analysis & Monitoring

### **Wireshark — Network Traffic Analysis**

* Packet-level inspection of network traffic
* Captures and analyzes real-time communication
* Provides deep visibility into protocols and sessions

**Focus Areas**

* Packet structure and protocol breakdown
* Identifying suspicious traffic patterns
* DNS, HTTP, TCP analysis
* Filtering and stream following

### **tcpdump — Command-Line Packet Capture**

* Captures raw network packets in real time
* Lightweight alternative to Wireshark
* Useful for quick inspection and remote analysis

**Focus Areas**

* Interface-based capture
* Protocol filtering (TCP, UDP, ICMP)
* Writing `.pcap` files for analysis
* Traffic debugging


### **Snort — Intrusion Detection & Prevention System (IDS/IPS)**

* Monitors network traffic for malicious activity
* Uses rule-based detection for threats
* Can operate in IDS or IPS mode

**Focus Areas**

* Rule creation and tuning
* Traffic analysis and alerting
* Signature-based detection
* Network defense monitoring


## Web Application Security

### **Burp Suite — Web Application Testing**

* Intercepts and manipulates HTTP/HTTPS traffic
* Analyzes request-response lifecycle
* Identifies vulnerabilities in web applications

**Focus Areas**

* Proxy interception and traffic analysis
* Request manipulation
* Authentication and session testing
* Input validation testing


### **Burp Repeater — Manual Request Testing**

* Sends and modifies HTTP requests manually
* Allows controlled testing of parameters
* Observes backend response behavior

**Focus Areas**

* Parameter manipulation
* Testing edge cases
* Identifying logic flaws (e.g., IDOR, injections)


### **Burp Intruder — Automated Input Testing**

* Performs automated attacks using payload lists
* Supports brute force and fuzzing techniques
* Identifies weak input validation

**Focus Areas**

* Payload injection strategies
* Brute force testing
* Parameter fuzzing
* Response comparison



##  Exploitation

### **Metasploit — Exploitation Framework**

* Framework for developing and executing exploits
* Provides modules for payloads and auxiliary tasks
* Validates and demonstrates real-world impact

**Focus Areas**

* Exploit selection and configuration
* Payload handling
* Session management
* Post-exploitation basics


##  Workflow Mapping

| Phase              | Tools                               |
| ------------------ | ----------------------------------- |
| Reconnaissance     | Nmap, Gobuster, DNSDumpster, Shodan |
| Enumeration        | Nmap, Burp Suite                    |
| Analysis           | Wireshark, tcpdump                  |
| Exploitation       | Metasploit                          |
| Web Testing        | Burp Suite (Repeater, Intruder)     |
| Defense/Monitoring | Snort                               |


