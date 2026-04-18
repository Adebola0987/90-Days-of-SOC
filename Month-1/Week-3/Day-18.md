# 📡 Day 18: ICMP Analysis (The Network's Heartbeat)

### 🔬 Technical Details
I analyzed **ICMP Type 8 (Echo Request)** and **Type 0 (Echo Reply)**. While vital for troubleshooting connectivity, these packets are also used by adversaries for network mapping.

### 🚩 Detection Scenario
A **Ping Sweep** (one IP sending Type 8 requests to every IP in a subnet) is a major indicator of an attacker performing network discovery. I am learning to identify these patterns to catch threats in the "Reconnaissance" phase of the Cyber Kill Chain.

**Evidence:**
> ⚠️ **INVESTIGATION IN PROGRESS:** Screenshot of ICMP echo request/reply sequence will be uploaded here.
