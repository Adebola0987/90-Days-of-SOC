#  Week 4 Summary: Windows Forensic Fundamentals

###  Learning Overview
This week, I transitioned from Network analysis to Host-Based Forensics. I learned how to investigate a Windows machine to find evidence of attacker activity.

###  Key Takeaways
* **Artifacts:** I learned that Windows creates "artifacts" (leftover data) for almost every action.
* **Prefetch (`.pf`):** This is the evidence of **Execution**. It proves a program was run, even if the program was later deleted.
* **The Registry:** Specifically the "Run Keys," which are the primary location for **Persistence**. I learned to audit `HKCU` to see what starts on login.

###  Tools & Skills
* **Regedit:** Used to manually audit system persistence.
* **File System Navigation:** Understanding the significance of suspicious file paths (e.g., `Temp`, `Public`, `AppData`).

###  Next Steps
Moving into **Week 5**, I will begin exploring **Linux Forensics** and mastering the Command Line (CLI) to hunt for threats on servers.
