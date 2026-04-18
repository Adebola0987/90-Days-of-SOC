# 🤝 Day 15: The TCP Three-Way Handshake

### 🔬 Objective
To analyze the fundamental mechanics of the **Transmission Control Protocol (TCP)** and understand how stateful connections are established.

### 🛡️ Analyst Analysis
Using Wireshark, I isolated the **SYN, SYN-ACK, and ACK** packets. This "handshake" is the backbone of reliable internet communication. From a SOC perspective, monitoring these flags helps us identify:
* **TCP Port Scanning:** Rapid SYN packets with no completion.
* **SYN Flooding:** A DDoS tactic aimed at exhausting server resources.

### 🖼️ Evidence
![TCP Handshake Analysis](./Evidence/TCP_Handshake_Evidence.png)
