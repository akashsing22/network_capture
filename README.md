# Network Traffic Analysis Using Wireshark

## Project Overview
This project demonstrates live network packet capture, protocol analysis (DNS, HTTP, ICMP), and security inspection using Wireshark on a Windows environment.

## Objective
* Capture and analyze unencrypted and encrypted network protocols.
* Filter traffic using Wireshark Display Filters to inspect packet headers and payloads.
* Understand network communications and identify potential unencrypted security risks.

---

## Tools Used
* **OS:** Windows 10/11
* **Packet Analyzer:** Wireshark v4.x
* **Capture Driver:** Npcap
* **Terminal:** Windows Command Prompt (CMD)

---

## Step-by-Step Execution

### 1. Packet Capture Setup
* Initialized capture on the active Wireless Network Interface (`Wi-Fi`).
* Generated sample traffic using standard web requests and CLI utilities (`nslookup`, `ping`).

### 2. Protocol Analysis

#### A. DNS Resolution Analysis
* **Filter:** `dns`
* Observed domain name queries sent over UDP port 53 to resolve domain names to IP addresses.

#### B. HTTP Plain-Text Inspection
* **Filter:** `http`
* Inspected HTTP GET/POST requests. Unencrypted payload contents (headers, host info, server responses) were fully readable via Wireshark's **Follow HTTP Stream** feature.

#### C. ICMP Echo Request/Reply
* **Filter:** `icmp`
* Verified standard ICMP echo requests generated during network diagnostic tests.

---

## Key Findings & Security Takeaways
1. **Risk of Cleartext Protocols:** HTTP traffic transmits data in plaintext without encryption. Anyone performing packet sniffing on the same local network can view sensitive payloads.
2. **Mitigation:** Organizations must enforce HTTPS (TLS/SSL) for all web communications to encrypt data in transit.

---

## How to Reproduce
1. Download Wireshark from the official website.
2. Open `network_capture.pcapng` from this repository in Wireshark to inspect the captured traffic.
