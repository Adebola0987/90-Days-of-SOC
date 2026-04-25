#  Day 26: Linux Fundamentals - The Analyst's Map

###  Objective
To master Linux filesystem navigation and identify key directories used in host-based forensic investigations.

###  Technical Concept: The Root Hierarchy
Unlike Windows (C:\), Linux starts at the **Root (/)**. Every piece of evidence is a file located somewhere on this tree.

### Practical Lab #1: Navigation & Discovery
* **Goal:** Locate system configuration and log files.
* **Commands Mastered:**
    * `pwd`: To verify current investigative position.
    * `ls -la`: To reveal hidden files (crucial for finding "dot" malware).
    * `cd`: To traverse the directory tree.
    * `cat`: To read text-based evidence without modifying it.

###  Investigation "Cheat Sheet" for SOC:
* **/var/log**: My first stop for evidence (auth logs, system logs).
* **/etc**: Where I check for unauthorized user accounts or modified configs.
* **/tmp**: The first place I check for suspicious scripts (world-writable).

###  Reflection
Today I learned that "Everything is a file" in Linux. If I can't find it with a GUI, I have to be able to find it with a path.
