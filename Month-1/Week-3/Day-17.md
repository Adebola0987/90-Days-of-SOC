# 📖 Day 17: DNS Analysis (UDP Port 53)

### 🔬 Technical Breakdown
DNS acts as the "Phonebook of the Internet." I analyzed how endpoints find servers and how attackers abuse this protocol.
* **UDP vs TCP:** DNS primarily uses UDP because it's faster for quick "lookup" questions.
* **A-Records:** I identified how a domain name is mapped to an IP address.

### 🛡️ Analyst Perspective
Attackers often use **DNS Tunneling** to sneak data out of a network because DNS traffic is rarely blocked by firewalls. Monitoring for high-frequency queries to unusual top-level domains (TLDs) is a key part of my threat hunting process.

**Evidence:**
> ⚠️ **INVESTIGATION IN PROGRESS:** Screenshot of DNS Query/Response packets will be uploaded here.
