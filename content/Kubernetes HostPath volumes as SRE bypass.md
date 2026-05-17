---
title: Kubernetes HostPath volumes as SRE bypass
aliases: ["hostPath bypass", "raw node storage"]
tags: ["kubernetes", "storage", "sre", "anti-pattern"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Kubernetes HostPath Volumes as SRE Bypass

When a CSI storage provisioner (like OpenEBS) is failing, an SRE can bypass the provisioner entirely by mapping a raw `hostPath` volume directly into the Pod.

```yaml
volumes:
- name: config
  hostPath:
    path: /var/hass-data
    type: DirectoryOrCreate
```

**Pros:** Removes the CSI and PVC abstraction layers; the Kubelet simply runs `mkdir` on the node's disk. Great for isolating storage bugs.

**Cons:** Introduces severe technical debt. The workload loses K8s storage mobility, snapshot capabilities, and storage limits. The pod must be strictly pinned to the node via `nodeSelector`.[^1]

---
[^1]: Kubernetes Documentation, "Volumes: hostPath".
