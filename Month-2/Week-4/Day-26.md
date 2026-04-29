#  Mastering Linux Log Parsing (Grep, Sed, Awk)

##  Objective
To transition from basic log viewing to advanced data manipulation and automated reporting. I focused on using the Linux "Power Trio" to identify security events within system logs.

---

##  Tools & Commands Mastered

### 1. Grep (The Filter)
Used to isolate specific security events.
* **Command:** `sudo journalctl -u ssh | grep "Failed password"`
* **Learning:** I learned how to "pipe" raw system output into grep to ignore irrelevant data and focus only on authentication failures.

### 2. Awk (The Data Surgeon)
Used to extract specific data columns and format reports.
* **Command:** `awk '{print "User: " $9 " | IP: " $11}'`
* **Learning:** I mastered column manipulation. I used `$9` and `$11` to pull out usernames and IP addresses. I also learned to use **`$NF`** to grab the final word of any log line (the executed command).

### 3. Sed (The Stream Editor)
Used for "Find and Replace" operations to clean or mask data.
* **Command:** `sed 's/Failed/FAILURE/g'`
* **Learning:** I practiced using `sed` to replace sensitive strings or reformat log status messages for better readability in reports.

---

