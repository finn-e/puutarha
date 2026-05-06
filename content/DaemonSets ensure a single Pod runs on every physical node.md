<<<<<<< HEAD
---
=======
>>>>>>> origin/trunk
publish: true
gemini: true
tags:
  - kubernetes
  - systems_thinking
<<<<<<< HEAD
created: '2026-05-04 17:00'
last_modified: '2026-05-04 17:00:00'
status: evergreen
confidence: fact
---
=======
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact
>>>>>>> origin/trunk

# DaemonSets ensure a single Pod runs on every physical node

For cluster-wide operations like logging or networking plugins (like Cilium), DaemonSets guarantee exactly one instance of a workload exists per server. This ensures uniformity across the hardware, acting as systemic redundancy.[^1]

[^1]: Kubernetes Documentation: DaemonSets.
