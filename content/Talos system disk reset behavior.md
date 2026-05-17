---
title: Talos system disk reset behavior
aliases: ["talosctl reset on bare metal", "SBC disk wiping"]
tags: ["talos", "hardware", "raspberry-pi", "storage"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Talos System Disk Reset Behavior

The `talosctl reset` command behaves fundamentally differently on bare-metal SBCs (like Raspberry Pis running off SD cards) compared to VMs or enterprise servers.

In a VM, a reset wipes the installation partition, but the hypervisor continues to present the boot ISO, allowing for immediate remote reprovisioning.

On a Raspberry Pi, the SD card *is* both the boot media and the system disk. Executing `talosctl reset` effectively formats the device's own brain. Upon reboot, the Pi will fail to find a bootloader, rendering it dead to the network until the SD card is physically pulled and re-flashed with the `metal-arm64.img`.[^1]

---
[^1]: Talos Linux Architecture, "Disk Partitioning and Upgrades".
