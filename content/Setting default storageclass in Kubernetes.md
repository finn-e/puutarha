---
title: Setting default storageclass in Kubernetes
aliases: ["PVC pending storageclass unset", "default storage provisioner"]
tags: ["kubernetes", "storage", "manifests", "sre"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Setting Default StorageClass in Kubernetes

If a PersistentVolumeClaim (PVC) lacks an explicit `storageClassName`, Kubernetes defaults to the cluster's default StorageClass. If no default exists, the PVC remains `Pending` indefinitely with its StorageClass showing `<unset>`.[^1]

## The Fix
Declare the provisioner as the cluster default via annotations to keep workloads storage-agnostic:

```bash
kubectl patch storageclass <sc-name> -p '{"metadata": {"annotations":{"storageclass.kubernetes.io/is-default-class":"true"}}}'
```

---
[^1]: Kubernetes Documentation, "Persistent Volumes: Default StorageClass".
