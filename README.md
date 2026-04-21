# 🌐 Network Traffic Analysis — SOC Analyst Portfolio Project 4

![Wireshark](https://img.shields.io/badge/Tool-Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white)
![Kali Linux](https://img.shields.io/badge/Platform-Kali%20Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

---

## 📌 Project Overview

This project demonstrates live network traffic capture and analysis using **Wireshark** on **Kali Linux** — a core skill for any SOC Analyst. A total of **13,481 packets** were captured on the eth0 interface and analyzed to identify protocols, DNS queries, HTTP traffic, and external IP communications.

This is exactly what a SOC analyst does when investigating suspicious network activity in a real environment.

---

## 🎯 Objectives

- Capture live network traffic using Wireshark on Kali Linux
- Analyze DNS traffic to identify domain lookups
- Examine HTTP and HTTPS traffic patterns
- Use Protocol Hierarchy statistics to understand traffic breakdown
- Identify external IP addresses communicating with the host
- Document all findings in a structured investigation report

---

## 🛠️ Tools Used

| Tool | Version | Purpose |
|------|---------|---------|
| Wireshark | 4.6.4 | Packet capture and traffic analysis |
| Kali Linux | 2026.1 | Analysis platform (VirtualBox VM) |
| Firefox | 140.0 | Traffic generation |
| VirtualBox | Latest | VM hypervisor |

---

## 🔬 Analysis Performed

### 1. 🟢 Live Packet Capture
- Launched Wireshark with root privileges
- Selected **eth0** interface for capture
- Browsed to google.com and youtube.com to generate traffic
- Captured **13,481 packets** over approximately 2 minutes
- Saved capture file as `network-traffic-analysis.pcapng`

### 2. 🔵 DNS Traffic Analysis
- Applied Wireshark filter: `dns`
- **304 DNS packets** identified (2.3% of total traffic)
- Domains resolved included: `clients4.google.com`, `oauthaccountmanager.googleapis.com`, `monetizemyapp.net`, `content-signature-2.cdn.mozilla.net`
- All DNS queries sent from host (192.168.0.138) to DNS server (49.205.72.130)

### 3. 🟡 HTTP Traffic Analysis
- Applied Wireshark filter: `http.request`
- **90 HTTP packets** identified
- Firefox browser identified via User-Agent: `Mozilla/5.0 (X11; Linux x86_64) Firefox/140.0`
- OCSP certificate verification traffic observed (normal browser security behaviour)
- SSDP broadcast traffic detected from local network device

### 4. 🟣 Protocol Hierarchy Statistics
- IPv6 dominated traffic at **72.1%**
- IPv4 accounted for **27.9%** of traffic
- TCP was the primary transport protocol at **64.7%**
- SSDP (device discovery) observed at **7.4%**

### 5. 🔴 IP Conversations Analysis
- External IP **34.107.221.82** identified — Google server (normal)
- Local broadcast to **239.255.255.250** — SSDP device discovery (normal)
- No suspicious or unknown external IPs identified

---

## 📊 Key Findings

| Finding | Details |
|---------|---------|
| Total Packets Captured | 13,481 |
| DNS Packets | 304 (2.3%) |
| HTTP Packets | 90 (0.7%) |
| Host IP | 192.168.0.138 |
| DNS Server | 49.205.72.130 |
| External IP | 34.107.221.82 (Google) |
| Dominant Protocol | IPv6 (72.1%) |
| Malicious Traffic | None identified |

---

## 🚨 Indicators of Compromise (IOCs)

No malicious indicators were found in this capture. All traffic was consistent with normal browsing activity.

| IOC Type | Value | Assessment |
|----------|-------|-----------|
| Host IP | 192.168.0.138 | Analyst machine — Benign |
| DNS Server | 49.205.72.130 | ISP DNS server — Benign |
| External IP | 34.107.221.82 | Google server — Benign |
| Local Device | 192.168.0.125 | Local network device — Benign |

---

## 📸 Evidence Screenshots

| # | Screenshot | Description |
|---|-----------|-------------|
| 1 | `screenshot-1-live-capture.png` | Wireshark live capture in progress on eth0 |
| 2 | `screenshot-2-full-packet-list.png` | All 13,481 captured packets |
| 3 | `screenshot-3-protocol-hierarchy.png` | Protocol Hierarchy Statistics |
| 4 | `screenshot-4-dns-filter.png` | DNS filter showing 304 packets |
| 5 | `screenshot-5-dns-expanded.png` | DNS packet details expanded |
| 6 | `screenshot-6-http-filter.png` | HTTP requests and responses |
| 7 | `screenshot-7-ip-conversations.png` | IP Conversations showing external IPs |

---

## 📄 Investigation Report

A full professional investigation report is included in this repository:
📎 `Network-Traffic-Analysis-Report.docx`

---

## 💡 What I Learned

- How to capture live network traffic using Wireshark
- How to use display filters to isolate specific protocols (dns, http, http.request)
- How to read and interpret DNS queries and responses
- How to identify external IP addresses from network conversations
- How to use Protocol Hierarchy to understand traffic distribution
- The difference between HTTP and encrypted HTTPS/TLS traffic
- What normal vs suspicious network traffic looks like

---

## 🔗 My SOC Portfolio

| Project | Description |
|---------|-------------|
| [Project 1 — Phishing Email Investigation](https://github.com/Meenakshy10/phishing-email-investigation) | Analyzed phishing email using OSINT tools |
| [Project 2 — Mini Home Lab Setup](https://github.com/Meenakshy10/Mini-Home-Lab-Setup) | Built cybersecurity home lab from scratch |
| [Project 3 — Brute Force Attack Detection](https://github.com/Meenakshy10/brute-force-attack-detection) | Detected RDP brute force attack using Hydra |
| **Project 4 — Network Traffic Analysis** | **Live packet capture and analysis with Wireshark** |

---

*SOC Analyst Portfolio — Meenakshy | Built on Kali Linux*
