# 🪟 Day 22: Windows Forensics - The Registry & Persistence

### 🎯 Objective
Investigating how attackers use the Windows Registry to maintain access.

### 🕵️‍♂️ Investigation: The Registry "Run" Keys
I explored the `HKEY_CURRENT_USER` hive to identify startup programs.

![Registry Persistence Search](./Evidence/RUN_KEYS.png)

**Findings:**
* The entry for **OneDrive** is legitimate, pointing to the user's AppData folder.
* I learned that attackers use this same "Run" key to hide malicious scripts.
* **HKCU** is a high-value target because it can be modified without an Admin/UAC prompt.
