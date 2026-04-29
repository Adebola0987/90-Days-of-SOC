# Day 5: The TCP Three-Way Handshake

Reliability is key in networking. Today I studied how TCP ensures a connection is solid before data is moved.

### The Steps:
1. SYN: Client asks to synchronize.
2. SYN-ACK: Server acknowledges and sends its own sync.
3. ACK: Client confirms the final handshake.

### The Security Threat:
A SYN Flood attack happens when a malicious actor sends thousands of SYNs but never sends the final ACK, causing the server to run out of memory.

### Active Recall:
- Q: What are the three steps of a TCP handshake?
- A: SYN, SYN-ACK, and ACK.
