---
title: SD card IOPS bottleneck in container creation
aliases: ["ContainerCreating hanging on bare metal", "Raspberry Pi SD card slow pull"]
tags: ["hardware", "kubernetes", "performance", "storage"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# SD Card IOPS Bottleneck in Container Creation

When deploying heavy containers (like Home Assistant, ~1.5GB) to a bare-metal node running off a microSD card, the Pod may sit in the `ContainerCreating` status for several minutes.

This is rarely a network issue. The Kubelet has downloaded the image layers and is extracting them. SD cards have notoriously terrible random write IOPS compared to SSDs/NVMe drives.[^1] The containerd runtime is effectively bottlenecked by the physical hardware's write latency during decompression.

---
[^1]: Raspberry Pi Foundation, "Storage Benchmarks".
