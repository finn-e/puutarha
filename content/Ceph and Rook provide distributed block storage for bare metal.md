<<<<<<< HEAD
---
=======
>>>>>>> origin/trunk
publish: true
gemini: true
tags:
  - kubernetes
  - homelab
  - site_reliability
<<<<<<< HEAD
created: '2026-05-04 17:00'
last_modified: '2026-05-04 17:00:00'
status: evergreen
confidence: stable
---
=======
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: stable
>>>>>>> origin/trunk

# Ceph and Rook provide distributed block storage for bare metal

Running Ceph via the Rook operator aggregates the individual NVMe drives across the Raspberry Pi cluster into a single, highly available storage pool. This software-defined storage layer is crucial because [[Persistent Volume migration is the hardest part of cluster upgrades]].[^1]

[^1]: Rook Documentation. Ceph Storage for Kubernetes.
