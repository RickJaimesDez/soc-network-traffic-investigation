# SOC Network Traffic Investigation

This project documents a structured SOC-style investigation of malware-related network traffic using a public packet capture.

The objective was to:
- Identify the infected internal host
- Confirm malicious payload delivery
- Analyze encrypted follow-on communications
- Extract actionable indicators of compromise (IOCs)

---

## Environment

- Windows 10 Virtual Machine (VirtualBox)
- Wireshark for packet analysis

---

## Dataset

2025-06-20-traffic-from-running-the-malware.pcap  
Source: Malware-Traffic-Analysis.net

---

## Key Findings

- Successful HTTP retrieval of `/shrk.bin`
- `200 OK` response confirming payload delivery
- Repeated TLS Client Hello sessions to `b1.encountergulf.world`
- Encrypted communication preceding visible payload download
- Single-host impact (172.16.1.128)
- No DNS visibility within capture window
- External threat intelligence validation of observed infrastructure

---

## Indicators of Compromise (IOCs)

Internal Host:
- 172.16.1.128

External IP:
- 104.21.21.29

Domains:
- h4.chatterscaled.top
- b1.encountergulf.world

Follow-up Payload:
- URL: http://h4.chatterscaled.top/shrk.bin
- SHA256: 21d0bd2f5870c46cafa2a3ac4771ce0d907e1e03b926ae8820298f639e3b4fb6
- File Size: 8,359,712 bytes

---

## Full Investigation Writeup

Structured SOC-style report available here:

https://rickjaimesdez.github.io/writeups/network-traffic-investigation/
