<<<<<<< HEAD
---
=======
>>>>>>> origin/trunk
publish: true
gemini: true
tags:
  - kubernetes
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

# Persistent Volume migration is the hardest part of cluster upgrades

While stateless pods can simply be killed and rescheduled on a new Talos node, stateful databases tied to physical host paths must be carefully backed up and restored. This data gravity is an absolute constraint.[^1]

[^1]: CNCF. Challenges in Stateful Workloads.
