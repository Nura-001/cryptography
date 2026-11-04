# Cryptography 4115 – Wireshark Traffic Analysis

## Student Information

- **Name:** Nurjahan Akter
- **ID:** IT-23045
- **Department:** ICT
- **University:** Mawlana Bhashani Science and Technology University (MBSTU)
- **Course:** Cryptography 4115

## Project Overview

This project focuses on analyzing network traffic using Wireshark. The main objective is to observe network packets while accessing a website and understand the protocols used during communication.

## Tools Used

- Wireshark 4.6.9
- Npcap
- Google Chrome
- Windows 11

## Experiment

The network traffic was captured while visiting:

**Website:** https://www.google.com

The captured packets were analyzed to identify protocols such as TCP, TLS, UDP, DNS, and IPv4.

## Wi-Fi Capture Results

| Measurement | Result |
|---|---:|
| Total Packets | 135 |
| IPv4 Packets | 131 |
| TCP Packets | 122 |
| TLS Packets | 35 |
| UDP Packets | 9 |
| Standard DNS Packets | 4 |
| mDNS Packets | 3 |
| Capture Duration | Approximately 48 seconds |

## Protocol Analysis

- **IPv4:** Provides addressing and routing for network communication.
- **TCP:** Provides reliable data transmission.
- **TLS:** Helps secure communication through encryption.
- **UDP:** Supports connectionless data transmission.
- **DNS:** Converts domain names into IP addresses.
- **mDNS:** Supports local network name discovery.

## Wi-Fi and Ethernet Comparison

The Wi-Fi traffic was captured and analyzed successfully. An Ethernet capture could not be performed because a physical Ethernet connection was unavailable during the experiment.

Therefore, this project does not claim that the Wi-Fi and Ethernet results were experimentally compared.

## Repository Contents

- `README.md` – Project description and experiment summary.
- `WiFi_Ethernet_Comparison_Nurjahan_Akter.docx` – Comparison table.
- `Screenshots/` – Wireshark capture and analysis screenshots.

## Conclusion

This experiment provided practical experience in capturing and analyzing network traffic using Wireshark. It helped identify common network protocols and understand how data travels through a network.

---

**Submitted by:** Nurjahan Akter  
**Student ID:** IT-23045  
**Department of ICT, MBSTU**
