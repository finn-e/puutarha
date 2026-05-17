---
title: Talos bare-metal static IP bootstrapping
aliases: ["Talos static IP injection", "bare-metal DHCP trap"]
tags: ["kubernetes", "talos", "networking", "bare-metal", "sre"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Talos Bare-Metal Static IP Bootstrapping

When provisioning immutable infrastructure like Talos Linux on bare-metal Single Board Computers (SBCs), relying on a router's DHCP is an anti-pattern. If a node restarts and the DHCP lease expires, the node receives a new IP, breaking the `cluster.controlPlane.endpoint` hardcoded into the cluster's configuration.

Furthermore, executing a `talosctl reset` completely formats the system disk, deleting the OS and returning the node to a blank state where it will grab a random DHCP address upon reboot.

## The Injection Boot
To lock the infrastructure, inject static IPs during the initial configuration phase by patching the network interfaces against the temporary DHCP addresses.

```bash
talosctl apply-config --insecure \
  --nodes <TEMP_DHCP_IP> \
  --file controlplane.yaml \
  --config-patch @cp-patch.yaml
```

The node will accept the config, apply the static IP to its physical interface (e.g., `end0`), instantly drop the DHCP lease, and reboot on its permanent address.[^1]

---
[^1]: Talos Linux Documentation, "Getting Started: Bare Metal".
