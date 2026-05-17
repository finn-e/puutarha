---
title: Explicit dependencies in infrastructure as code
aliases: ["Hardcoding StorageClass", "IaC explicitness"]
tags: ["iac", "sre", "kubernetes", "manifests"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Explicit Dependencies in Infrastructure as Code

Relying on implicit environment states (like assuming a cluster has a "default" StorageClass) introduces fragility into Infrastructure as Code (IaC). If the cluster state is reset or the environment changes, the manifest fails silently (e.g., PVCs stuck in `Pending`).

In SRE practices, explicit declaration is always preferred over implicit assumptions. Hardcoding `storageClassName: openebs-hostpath` directly into the PVC manifest ensures the dependency contract is defined in the code, rather than relying on the cluster's hidden mutable state.[^1]

---
[^1]: Google SRE Book, "Simplicity: SRE's Core Value".
