I developed a Bash-based forensic tool, hunter.sh, to automate the detection of unauthorized access, suspicious processes, and persistence mechanisms on Linux systems. This project demonstrates practical application of SIEM-lite logic and Threat Hunting concepts covered in the Google Cybersecurity Professional Certificate.

Technical Breakdown & Proof
1. The Logic (Source Code)
I utilized Bash scripting to create a multi-stage pipeline. The script audits the "System State" (Processes & Connections) and parses system logs for brute-force patterns.

ss.png

Description: Viewing the script logic in Nano, showcasing the use of ps, ss, and journalctl piped into awk for log extraction.

2. Real-Time Threat Identification
During a live run, the script successfully identified unauthorized login attempts by parsing the SSH authentication logs.

hunter 2.png

Description: Script execution output showing 3 invalid user attempts from a 'nonexistentuser', demonstrating the automated log analysis feature.

3. Persistence Audit
The tool automatically scans for "Hidden Keys" by auditing user-level and system-wide Cron directories.



