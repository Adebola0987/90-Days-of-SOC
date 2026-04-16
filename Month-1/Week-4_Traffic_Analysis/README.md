# 📡 Week 4: Network Traffic Analysis Lab
**Date:** April 16, 2026  
**Tools Used:** Kali Linux, Wireshark, Mozilla Firefox  

## 🛡️ Executive Summary
In this lab, I performed a deep-packet inspection of network traffic to understand the fundamental mechanics of the TCP protocol. My goal was to isolate the connection establishment phase (The Three-Way Handshake) and analyze the security risks associated with unencrypted HTTP traffic (Cleartext Exposure).

---

## 🤝 Lab 1: The TCP Three-Way Handshake (The Greeting)
**Objective:** Capture and verify the "SYN, SYN-ACK, ACK" sequence between my local machine and a remote server.

### 🕵️‍♂️ Technical Analysis:
* **Filter Used:** `tcp.flags.syn == 1`
* **Observation:** I isolated **Packet 526**, which represents the `[SYN, ACK]` response. 
* **The Logic:** My Kali machine sent a `SYN` (Synchronize) to knock on the door. The server responded with a `SYN-ACK` to acknowledge my request and synchronize back. 
* **Security Insight:** Monitoring handshakes is vital for a SOC Analyst to detect **SYN Flood Attacks**, where an attacker attempts to overwhelm a server by leaving thousands of connections "half-open."

### 🖼️ Evidence: Handshake Capture
![TCP Handshake Analysis](VirtualBox_kali-linux-2026.1-virtualbox-amd64_16_04_2026_14_16_48.jpg)

---

## 🕵️‍♂️ Lab 2: Follow the Stream (Cleartext vs. Encryption)
**Objective:** Reconstruct a full conversation using Wireshark’s "Follow TCP Stream" feature to identify sensitive data leakage.

### 🕵️‍♂️ Technical Analysis:
* **The Request (Red Text):** My machine sent an `HTTP GET` request for `success.txt`. The `User-Agent` reveals I am using Firefox on Linux, which provides "Fingerprinting" data an attacker could use to target specific browser vulnerabilities.
* **The Response (Blue Text):** The server identifies itself as `nginx` and returns a `200 OK` status, delivering the file content.
* **Security Risk:** Because this was conducted over **Port 80 (HTTP)**, the data is sent in **Cleartext**. As shown in the evidence below, the word "success" is completely visible. In a real-world scenario, this could have been a password or a session cookie.

### 🖼️ Evidence: Reconstructed HTTP Stream
![HTTP Stream Analysis](VirtualBox_kali-linux-2026.1-virtualbox-amd64_16_04_2026_14_40_00.png)

---

## 🚀 Key Takeaways & Mitigation
1. **Visibility:** Using Wireshark, I was able to "see the truth" on the wire, proving that headers and payloads are easily intercepted on unencrypted networks.
2. **The Fix:** To mitigate this risk, organizations must enforce **HTTPS (Port 443)** using TLS encryption. This wraps the "Red and Blue" text in an encrypted tunnel, making it unreadable to unauthorized interceptors.
