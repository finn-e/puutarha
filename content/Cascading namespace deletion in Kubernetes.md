---
title: Cascading namespace deletion in Kubernetes
aliases: ["Deleting a namespace deletes everything", "Accidental label removal"]
tags: ["kubernetes", "namespaces", "sre", "pitfalls"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Cascading Namespace Deletion in Kubernetes

When troubleshooting a broken deployment, executing `kubectl delete -f manifest.yaml` will delete all resources defined in that file. If the manifest includes a `Namespace` definition, Kubernetes will trigger a cascading deletion of the entire namespace and *all* objects within it.[^1]

This is dangerous because it destroys out-of-band configurations applied to that namespace, such as Pod Security Admission labels (`pod-security.kubernetes.io/enforce=privileged`). 

When the manifest is reapplied, the namespace is recreated as a blank slate, restoring the default restrictive security posture and breaking workloads that rely on host-level access.

---
[^1]: Kubernetes Documentation, "Namespaces: Deleting a Namespace".
