<<<<<<< HEAD
---
=======
>>>>>>> origin/trunk
publish: true
gemini: true
tags:
  - kubernetes
  - systems_thinking
  - homelab
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

# Migrating from MicroK8s to Talos requires rolling node replacement

To transition a live home cluster without catastrophic downtime, the migration must be executed by removing one Raspberry Pi at a time, flashing the new OS, and rejoining it to the cluster. This relies heavily on the fact that [[Rolling migrations prevent homelab downtime]].[^1]

[^1]: OneUptime. (2026). Migrate from MicroK8s to Talos Linux.
