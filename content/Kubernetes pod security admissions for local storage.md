---
title: Kubernetes pod security admissions for local storage
aliases: ["Talos privileged namespace", "PSA restricted profile bypass"]
tags: ["kubernetes", "security", "talos", "storage"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Kubernetes Pod Security Admissions for Local Storage

Security-hardened Kubernetes distributions enforce strict Pod Security Admissions (PSA), defaulting to the `restricted` profile.[^1]

Local storage provisioners (like OpenEBS or Mayastor) require host-level privileges to interact with the physical node's disk (`hostNetwork=true`, `allowPrivilegeEscalation=true`). If deployed into a restricted namespace, the admission controller silently blocks pod creation, stranding PVCs in a `Pending` state.

## The Fix
Label the namespace to allow privileged workloads *before* deploying the provisioner:

```bash
kubectl label namespace openebs pod-security.kubernetes.io/enforce=privileged
kubectl label namespace openebs pod-security.kubernetes.io/audit=privileged
kubectl label namespace openebs pod-security.kubernetes.io/warn=privileged
```

---
[^1]: Kubernetes Documentation, "Pod Security Admission".
