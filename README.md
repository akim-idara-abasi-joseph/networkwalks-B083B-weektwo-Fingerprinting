# Week 2 Report – Footprinting & Network Scanning

## 1. Liability Disclaimer

I have performed these activities only on the systems and devices where I had secured written permission or on systems that I own personally. These activities were carried out strictly for educational purposes as part of my Cybersecurity & Ethical Hacking internship. Unauthorized access or scanning of systems without permission is illegal and unethical.

---

## 2. Introduction

This report covers footprinting the **networkwalks.com** domain using Kali Linux tools (W2-PM1) and scanning my local network with Zenmap (W2-PM5) as part of Week 2 of my Networkwalks internship. The activities demonstrate how public information gathering and network scanning are used during the reconnaissance phase of cybersecurity.

---

## 3. Tools Used

| Tool | Purpose |
|------|---------|
| Kali Linux & Windows | Operating systems used for reconnaissance activities |
| WHOIS | Find domain registration details (owner, dates, name servers) |
| WhatWeb | Fingerprint web technologies (server, CMS, plugins, IP) |
| Nslookup | Resolve the domain name to its IP address using DNS |
| Curl -I | Read HTTP response headers |
| Wafw00f | Detect whether a Web Application Firewall protects the site |
| DNSRecon | Enumerate DNS records (NS, MX, SPF, TXT, SRV) |
| Zenmap (Nmap GUI) | Scan the local subnet to identify live hosts, IP addresses and MAC addresses |
| Windows CMD | Identify local IP address and subnet |

---

## Internship Details

| Item | Details |
|------|---------|
| **Pentester** | Akim Idara-Abasi Joseph |
| **Program / Batch** | B083 – Networkwalks |
| **Date** | 24 September 2026 |
| **Modules Completed** | W2-PM1 (Multiple Kali Tools), W2-PM5 (Zenmap Scanning) |
| **Target** | Networkwalks Domain & Personal Local Network |
| **Permission Obtained** | Yes |
| **Phases Covered** | Reconnaissance, Footprinting & Network Discovery |

---

# 4. Activities Performed

## 4.1 Footprinting & Reconnaissance

I performed reconnaissance against the **networkwalks.com** domain using the following Kali Linux tools:

- WHOIS
- WhatWeb
- Nslookup
- Curl
- Wafw00f
- DNSRecon

Each tool collected different information about the target, including domain registration details, web technologies, IP address, HTTP headers, WAF detection, and DNS records.

---

## 4.2 Network Scanning with Zenmap

I used **Command Prompt** to determine my local IP address and subnet.

```cmd
ipconfig
```

My network information was:

- **IPv4 Address:** 192.168.1.100
- **Subnet Mask:** 255.255.255.0
- **Default Gateway:** 192.168.1.1

Using the subnet mask, I determined that my network was:

```
192.168.1.0/24
```

I then performed a **Ping Scan** in Zenmap using:

```bash
nmap -sn 192.168.1.0/24
```

### Live Hosts Discovered

- 192.168.1.1
- 192.168.1.100
- 192.168.1.110
- 192.168.1.126
- 192.168.1.129

The scan also displayed the MAC addresses of the discovered devices and allowed me to generate a network topology.

---

# 5. Risk Analysis

| Finding | Evidence | Potential Impact | Risk |
|---------|----------|------------------|------|
| Web technologies exposed | WhatWeb | Technology fingerprinting | 🟡 Medium |
| Server IP identified | Nslookup | Infrastructure disclosure | 🟢 Low |
| HTTP headers exposed | Curl | Information disclosure | 🟢 Low |
| WAF detected | Wafw00f | Security architecture disclosure | 🟢 Low |
| DNS records exposed | DNSRecon | Infrastructure mapping | 🟡 Medium |
| Multiple active hosts discovered | Zenmap | Unknown devices may exist on the network | 🟡 Medium |

---

# 6. Recommendations

1. Monitor publicly available technology information.
2. Keep software and plugins updated.
3. Review HTTP response headers regularly.
4. Audit DNS records periodically.
5. Maintain and monitor the Web Application Firewall (WAF).
6. Conduct regular internal network scans.
7. Investigate any unknown devices.
8. Keep network documentation up to date.
9. Perform security assessments only with proper authorization.

---

# 7. Conclusion

During Week 2 of my Cybersecurity & Ethical Hacking internship, I completed practical exercises in footprinting, reconnaissance, and network scanning. Using Kali Linux tools such as WHOIS, WhatWeb, Nslookup, Curl, Wafw00f, and DNSRecon, I learned how to gather publicly available information about a target domain. I also used Zenmap to scan my local network, identify active hosts, collect IP and MAC address information, and generate a network topology.

These activities improved my understanding of reconnaissance as the first phase of a security assessment. They also strengthened my ability to document technical findings and reinforced the importance of performing security assessments only within an authorized environment.

---

# 8. Evidence

> Insert screenshots of:
>
> - WHOIS
> - WhatWeb
> - Nslookup
> - Curl
> - Wafw00f
> - DNSRecon
> - `ipconfig`
> - Zenmap Scan Results
> - Zenmap Topology
