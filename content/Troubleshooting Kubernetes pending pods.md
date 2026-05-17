---
title: Troubleshooting Kubernetes pending pods
aliases: ["Why is my pod pending", "FailedScheduling events"]
tags: ["kubernetes", "debugging", "sre"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Troubleshooting Kubernetes Pending Pods

When a Pod is stuck in `Pending` state, it means the Kubernetes Scheduler cannot find a suitable node that satisfies all the Pod's requirements.[^1]

The fastest way to diagnose scheduling failures is to check the Pod's event log:

```bash
kubectl describe pod <pod-name> -n <namespace> | tail -n 15
```

The `Events:` block will output a `FailedScheduling` reason, explicitly listing why nodes were rejected (e.g., "0/3 nodes available: pod has unbound immediate PersistentVolumeClaims", taints, or insufficient CPU).

---
[^1]: Kubernetes Documentation, "Pod Lifecycle: Pod Phase".
