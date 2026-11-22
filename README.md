# Week2-project-2
Project-2
# 🐉 Footprinting & Network Scanning with Kali Linux

## 📝 Project Overview
This repository documents my Week 2 project for the **Networkwalks Cybersecurity Internship (Batch B082)**. The project focuses on the reconnaissance phase of a penetration test, divided into two main modules:
1. **Footprinting & Reconnaissance:** Using multiple Kali Linux tools to gather open-source intelligence (OSINT) on a public target (`networkwalks.com`).
2. **Network Scanning:** Using Zenmap (Nmap GUI) to discover live hosts and enumerate open ports on a local network.

> **⚠️ Legal Disclaimer:** This project was conducted strictly for educational purposes under the **Networkwalks Letter of Authorization (NW-LOA-B082-017)**. All scans were limited to the authorized target (`networkwalks.com`) and the tester's own local area network (LAN). No exploitation or disruptive activities were performed.

---

## 🛠️ Part 1: Footprinting with Multiple Kali Tools (W2-PM1)
The goal of this phase was to map the digital footprint of the target domain using six different tools to gather DNS records, server information, and WAF detection.

### 1. WHOIS
Queries domain registration databases to find ownership and registration details.
```bash
whois networkwalks.com
2. NSLOOKUP
Queries the Domain Name System (DNS) to find the IP address and mail servers of the domain.

bash
nslookup networkwalks.com
3. WhatWeb
Fingerprints the web server to identify the CMS, server software, JavaScript libraries, and versions running on the site.

bash
whatweb -v https://networkwalks.com
4. cURL
Transfers data from a server. Here, it is used to inspect the HTTP response headers to identify the server type and check for security headers.

bash
curl -I https://networkwalks.com
5. Wafw00f
Detects and identifies Web Application Firewalls (WAF) protecting the target website.

bash
wafw00f https://networkwalks.com
6. DNSRecon
A powerful DNS enumeration script that checks for standard records and attempts zone transfers.

bash
dnsrecon -d networkwalks.com -t standard
🌐 Part 2: Zenmap Based Network Scanning (W2-PM5)
This phase focused on active scanning of a controlled local network to identify active devices and potential entry points.

Step 1: Identify Local Subnet
First, I identified my local IP address and subnet mask to define the scan scope.

bash
ip addr
Step 2: Host Discovery (Ping Scan)
Using Zenmap, I performed a Ping Scan (-sn) across the subnet (e.g., 192.168.1.0/24) to identify live hosts without performing port scans.

Zenmap Profile: Ping scan

Step 3: Intense Scan
Once live hosts were identified, I ran an "Intense Scan" (-T4 -A -v) against a specific target IP to perform OS detection, version detection, and script scanning.

Zenmap Profile: Intense scan

Key Findings: The scan revealed open ports (e.g., SSH on port 22, HTTP on port 80) and helped identify the operating system of the target host.

📊 Summary of Findings
Information Disclosure: The footprinting tools revealed that the target website utilizes specific web technologies and is hosted on a particular IP address.

Network Exposure: The Zenmap scans successfully identified active devices on the local network and highlighted open ports that could be potential vectors if left unpatched.

🚀 Tools Used
Kali Linux (Attacker Machine)

Oracle VirtualBox (Virtualization)

WHOIS, NSLOOKUP, WhatWeb, cURL, Wafw00f, DNSRecon, Zenmap.

Author: [Your Name]
Batch: B082 - Networkwalks Cybersecurity Internship

text

### 💡 How to customize this for your GitHub:
1.  **Add Screenshots:** Where it says `### 1. WHOIS`, you can drag and drop a screenshot of your terminal output right below it. Visuals make a README look much more professional.
2.  **Update the Author Section:** Replace `[Your Name]` at the bottom with your actual name or GitHub handle.
3.  **Add Findings (Optional):** If you want to make it even better, you can add a small section called "Notable Findings" and list 1 or 2 interesting things you found (e.g., *"WhatWeb revealed the site is running WordPress version X"*). Just remember not to post any sensitive data!
