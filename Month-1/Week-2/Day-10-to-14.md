Days 10 - 14: Advanced Windows Telemetry & Cloud Investigations

Focus: Mastering Process Lineage, Digital Hashing, and Network Correlation.

 1. The "Parent-Child" Logic (Process Monitoring)
I learned that a process name (like svchost.exe) isn't enough to prove it's safe. I must look at its Parent.

Normal: services.exe → svchost.exe (System starting a service).

Suspicious: uTorrent.exe or Word.exe → svchost.exe (A user app starting a system process to hide).

Tool Used: Windows Event ID 4688 and Sysmon Event ID 1.

 2. Digital Fingerprinting (Hashing)
I practiced using Sysmon to see what regular Windows logs miss: The Hash.

The Technique: Even if a hacker renames malware.exe to Notepad.exe, the SHA256 Hash remains the same.

The Workflow: I extracted hashes from logs and verified them against VirusTotal to confirm file reputation.

Critical Lesson: A "Clean" hash in a "Dirty" location (like C:\Users\Public\Temp) is still a major Red Flag.

 3. Network "Phone Bill" Analysis
I used Event ID 3 to track where data is going.

Finding "Outliers": While Port 443 (Web) is normal, seeing Port 3389 (RDP) or Port 22 (SSH) being used by a non-admin app like Calculator.exe is an immediate alert.

Correlation: I learned to link a Network Connection (ID 3) back to the Process (ID 1) that started it.
