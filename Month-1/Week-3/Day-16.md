# 🕵️‍♂️ Day 16: Protocol Analysis - The Danger of Port 80

### 🔬 Technical Breakdown
I practiced **Stream Reassembly**. Network traffic is sent in tiny fragments; however, using Wireshark’s "Follow TCP Stream" feature, I am able to reconstruct the entire conversation between the user and the website.

### 🚩 The Security Risk
Because **HTTP (Port 80)** does not use encryption (TLS/SSL), I can see the following in cleartext during an investigation:
* **User-Agent strings:** Identifying the victim's OS and Browser version.
* **Server Headers:** Identifying the specific web server version.
* **POST Data:** This is where sensitive data like credentials can be intercepted.

### 🛡️ Analyst Perspective
As a SOC Analyst, if I detect HTTP traffic on a sensitive segment of the network, my first action is to recommend a **Force-HTTPS** policy. Unencrypted traffic is an open invitation for "Man-in-the-Middle" attacks.

**Evidence:**
> ⚠️ **INVESTIGATION IN PROGRESS:** Screenshot of HTTP GET request and reconstructed stream will be uploaded here.
