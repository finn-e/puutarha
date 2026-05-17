---
title: Volume binding mode: waitforfirstconsumer
aliases: ["Local storage pending PVC", "volumeBindingMode"]
tags: ["kubernetes", "storage", "scheduling"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Volume Binding Mode: WaitForFirstConsumer

In Kubernetes, cloud storage (like AWS EBS) typically uses `volumeBindingMode: Immediate`, creating the volume as soon as the PVC is requested.

Local storage provisioners (OpenEBS, Mayastor) must use `WaitForFirstConsumer`. Because local storage is physically tied to a specific node, the provisioner refuses to create the volume until the Kubernetes scheduler evaluates node resources and decides *which* node the Pod will run on.[^1]

If a local PVC is stuck in `Pending` but the StorageClass is correctly assigned, it indicates the bottleneck is the Pod's inability to schedule onto a node.

---
[^1]: Kubernetes Documentation, "Storage Classes: Volume Binding Mode".
