publish: true
gemini: true
tags:
  - kubernetes
  - site_reliability
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact

# Rolling migrations prevent homelab downtime

By cordoning and draining a single node, shifting workloads, and upgrading the base OS, a cluster maintains quorum and application availability. This methodical SRE practice ensures that [[High-quality infrastructure is invisible when working correctly]].[^1]

[^1]: Kubernetes Documentation. Safely Draining a Node.
