# Task 3: Network Packet Analysis Using Wireshark

## 📌 Overview

This task focuses on capturing and analyzing network traffic using **Wireshark** in a controlled cybersecurity lab environment.

The analysis covers common network protocols and communication patterns, including:

- DNS queries and responses
- TCP three-way handshake
- TCP flags
- HTTP communication
- Packet structure and protocol layers
- Identification of unusual or suspicious traffic patterns

The objective is to understand how network communication occurs at the packet level and how Wireshark can be used during network monitoring and cybersecurity investigations.

---

## 🎯 Objective

The objective of this task is to capture and analyze network packets and identify important protocol-level information.

The analysis includes:

1. Capturing live network traffic.
2. Identifying DNS communication.
3. Analyzing the TCP three-way handshake.
4. Examining TCP flags.
5. Capturing and analyzing HTTP traffic.
6. Inspecting packet headers and protocol layers.
7. Reviewing traffic for unusual or suspicious patterns.

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| Kali Linux | Cybersecurity testing environment |
| Wireshark | Packet capture and network traffic analysis |
| Terminal | Generating network traffic and testing connectivity |
| Web Browser | Generating HTTP traffic |
| Metasploitable 2 | Authorized local test target for network traffic generation |

---

## 🧪 Lab Environment

The packet analysis was performed in an isolated and authorized VirtualBox laboratory environment.

| Machine | Role | IP Address |
|---|---|---|
| Kali Linux | Analysis Machine | `192.168.56.101` |
| Metasploitable 2 | Test Target | `192.168.56.102` |

Network:

```text
192.168.56.0/24
