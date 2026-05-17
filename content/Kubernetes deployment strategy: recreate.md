---
title: Kubernetes deployment strategy: recreate
aliases: ["Recreate vs RollingUpdate", "SQLite locked database K8s"]
tags: ["kubernetes", "deployments", "storage"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Kubernetes Deployment Strategy: Recreate

The default Kubernetes Deployment strategy is `RollingUpdate`, which ensures zero-downtime by spinning up the new Pod before killing the old one.

For stateful workloads utilizing local SQLite databases (like Home Assistant), `RollingUpdate` causes severe corruption or `database is locked` errors. The new Pod will attempt to mount the `ReadWriteOnce` PVC and write to the database while the old Pod still holds the file locks.[^1]

**The Fix:** Stateful deployments relying on simple file locks must use `strategy: type: Recreate`. This forces K8s to terminate the old Pod, release the volume locks, and *then* spin up the new Pod.

---
[^1]: Kubernetes Documentation, "Deployments: Strategy".
