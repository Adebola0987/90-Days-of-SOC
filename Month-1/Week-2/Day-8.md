# 🛡️ Day 8: Windows Event ID Mastery (Deep Dive)

### 📅 Date: April 10, 2026
**Focus:** Comprehensive analysis of Windows Security Logs and Attack Chain Logic.

---

## 🧠 Core Concepts Mastered
Today I learned that SOC Analysts must go beyond simple ID numbers to understand the "Intent" and "Persistence" behind an action.

### 1. Authentication & Access
* **Event 4624:** Success! I now understand **Logon Type 10** (RDP) vs **Type 2** (Interactive).
* **Event 4625:** Failed logon. Used to detect **Brute Force** patterns.
* **4672:** Special Privileges (The "God Mode" check).

### 2. Staying Inside (Persistence)
* **Event 4697 (Service Installation):** High danger! Services start automatically on boot. If a "Junior Analyst" installs one, it's a major red flag.
* **Event 4698 (Scheduled Task):** Malicious "alarm clocks" that hackers use to stay in the system.

### 3. The "Action" & "Cover-up"
* **Event 4688 (New Process):** Specifically looking for **Parent-Child** anomalies (e.g., `winword.exe` spawning `cmd.exe`).
* **Event 1102 (The Smoking Gun):** Log Cleared. The ultimate sign of a guilty attacker trying to hide evidence.

---

## 🕵️ Logic Scenario: The Insider Threat
I analyzed a scenario where a user account performed a sequence of high-privilege actions. I identified that while **SeDebugPrivilege** is a power move, the **Service Installation (4697)** is the most dangerous because it ensures the attacker remains in control even after a system reboot.

---

## ✅ Progress Check
- [x] Deep understanding of the "Big 5" Windows IDs.
- [x] Mastered Logon Type logic for network vs. local access.
- [x] Documented logic for identifying "Persistence" and "Anti-Forensics."
