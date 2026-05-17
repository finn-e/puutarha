---
title: Talos API discovery via Nmap
aliases: ["Finding unconfigured Talos nodes", "Talos port 50000"]
tags: ["talos", "networking", "nmap", "discovery"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Talos API Discovery via Nmap

When bare-metal Talos nodes boot for the first time, they lack a cluster configuration and often rely on DHCP. Unlike traditional servers with IPMI or predictable MAC-based DHCP reservations, SBCs must be discovered on the subnet.

Unconfigured Talos nodes expose their gRPC API on port `50000`.[^1]

## Scanning the Subnet
To find the temporary IP addresses of fresh nodes, use `nmap` to sweep the local subnet specifically for the open Talos API port:

```bash
nmap -p 50000 --open 192.168.1.0/24
```

---
[^1]: Talos Linux Documentation, "Talos API and Architecture".
