# Day 2: Understanding IP Addressing

Today I focused on how devices are identified on a network. Without IP addresses, data would have no way of finding its destination.

### Core Concepts:
- Public vs. Private IPs: My internal devices use Private IPs, but my router uses a Public IP to represent my network to the internet.
- NAT (Network Address Translation): This is a key security feature that hides our internal network structure from the outside world.

### Practical Learning:
I used the terminal on my MacBook to run `ip a` and `ifconfig` to see my own network configuration.

### Active Recall:
- Q: Does an external hacker see my Private IP or my Public IP?
- A: They only see the Public IP.
