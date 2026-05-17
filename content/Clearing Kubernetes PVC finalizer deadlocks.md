---
title: Clearing Kubernetes PVC finalizer deadlocks
aliases: ["PVC stuck terminating", "removing k8s finalizers"]
tags: ["kubernetes", "storage", "debugging", "sre"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Clearing Kubernetes PVC Finalizer Deadlocks

Kubernetes PVCs utilize **finalizers** (`kubernetes.io/pvc-protection`). During deletion, the API server places a lock on the object, waiting for the storage provisioner to confirm physical data destruction.[^1]

If the provisioner is offline or blocked by admission controllers, it never sends the signal. The PVC enters a deadlocked `Terminating` state, blocking new pods.

## The Fix
Patch the PVC metadata to strip the finalizer array, forcing immediate garbage collection:

```bash
kubectl patch pvc <pvc-name> -n <namespace> -p '{"metadata":{"finalizers":null}}'
```

---
[^1]: Kubernetes Documentation, "Storage Object in Use Protection".
