publish: true
gemini: true
tags:
  - kubernetes
  - site_reliability
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact

# The etcd key-value store is the absolute brain of Kubernetes

Every single piece of cluster state, from secret definitions to pod IPs, is stored in etcd. If this database is corrupted or loses quorum, the entire cluster suffers amnesia. This single point of truth shows why [[NVMe HATs resolve the SD card IO bottleneck]].[^1]

[^1]: CNCF etcd Documentation.
