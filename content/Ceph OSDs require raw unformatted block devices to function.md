publish: true
gemini: true
tags:
  - kubernetes
  - systems_thinking
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact

# Ceph OSDs require raw unformatted block devices to function

To build the Ceph storage cluster efficiently, the underlying NVMe drives on the Pi 5s cannot have file systems on them. Rook consumes the raw block device entirely, proving that [[First principles thinking strips assumptions]] about OS file management.[^1]

[^1]: Ceph Architecture and OSD Daemons.
