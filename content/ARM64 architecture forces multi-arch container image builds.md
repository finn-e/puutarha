<<<<<<< HEAD
---
=======
>>>>>>> origin/trunk
publish: true
gemini: true
tags:
  - kubernetes
  - software_engineering
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

# ARM64 architecture forces multi-arch container image builds

Running a Raspberry Pi cluster requires developers to compile software specifically for ARM64 architectures, exposing assumptions built into x86_64 workflows. Fixing these compatibility layers teaches how [[Abstractions leak at their boundaries]].[^1]

[^1]: Docker Multi-Architecture Build Documentation.
