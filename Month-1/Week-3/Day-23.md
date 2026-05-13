## Advanced Endpoint Monitoring with Sysmon ##
## Objective ##
To enhance Windows logging capabilities beyond standard Event Viewer defaults by deploying Microsoft Sysinternals Sysmon. This provides deep visibility into process creations, network connections, and file system changes—essential for detecting advanced persistent threats (APTs).

Technical Implementation
Tool: Sysmon (System Monitor)

Configuration: I Deployed Sysmon with a customized configuration file to filter out "noise" and focus on high-fidelity security events.

Key Event Captured: I also verified successful logging of Event ID 1 (Process Creation).

Evidence: Successfully tracked svchost.exe and other system processes, capturing critical metadata like ProcessGuid, Hashes, and ParentProcessId.
![Evidence Description](./sysmon.png)

Why Sysmon Matters for SOC Operations
Standard Windows Event Logs often miss the "how" and "why" of a process start. Sysmon fills these gaps by providing:

Process Lineage: Seeing exactly which program started another program (e.g., cmd.exe being launched by word.exe).

Network Visibility: Logging every connection an application makes to the internet.

Hash Verification: Recording SHA256 hashes of every running program to check against malware databases like VirusTotal.

Key Skills Demonstrated
Endpoint Detection & Response (EDR) Basics: Understanding how to monitor activity at the host level.

Log Analysis: Navigating Windows Event Viewer to identify and interpret Sysmon Operational logs.

System Administration: Installing and verifying low-level system drivers and services.
