# 🛡️ Day 9: Hunting with KQL (Kusto Query Language)

### 📅 Date: April 11, 2026
**Focus:** Understanding the logic of data filtering and performing a manual log investigation.

---

## 🧠 Core Concepts: From Zero to Logic
Today, I moved away from just "knowing" Event IDs to "finding" them using code. I learned that KQL is like a remote control for a giant library of security records.

### 1. The "Pipe" Logic (`|`)
The most important symbol in KQL. I learned to read this as **"and then."** It takes the big pile of data and funnels it into the next filter.

### 2. Essential Operators Mastered:
* **`where`**: The filter tool. Used to find specific IDs (like 4625) or specific Names.
* **`summarize count()`**: The counting tool. Used to turn a long list of logs into one clear number.
* **`project`**: The cleaning tool. Used to select only the columns that matter (Time, Computer, Account).

---

## 🛠️ Mini-Project: The "Guest Account" Investigation
**Objective:** Detect and count unauthorized access attempts on a specific workstation.

**Scenario:** I Analyzed a raw log dump from `Laptop-02` where multiple failed logins were reported. I developed the following query logic to aggregate the threat data:

```kql
SecurityEvent
| where EventID == 4625          // Filter for "Failed Logon" events
| where Account == "Guest_User"   // Narrow down to the specific suspect account
| summarize count()              // Total the number of attempts for analysis
