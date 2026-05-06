<<<<<<< HEAD
---
=======
>>>>>>> origin/trunk
publish: true
gemini: true
tags:
  - kubernetes
  - hardware
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

# NVMe HATs resolve the SD card IO bottleneck

Traditional Raspberry Pi clusters fail under database loads because microSD cards lack the random I/O performance required by Kubernetes etcd. By utilizing PCIe-based NVMe HATs and M.2 drives, the hardware bottleneck is fundamentally bypassed.[^1]

[^1]: PCIe Storage Benchmarks on ARM SBCs.
