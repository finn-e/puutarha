publish: true
gemini: true
tags:
  - kubernetes
  - site_reliability
  - systems_thinking
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact

# Talos removes SSH access to enforce infrastructure as code

By entirely removing the SSH daemon, Talos physically prevents engineers from logging in and making undocumented manual changes to the file system. This strict enforcement guarantees that [[Cloud infrastructure requires treating servers as cattle not pets]].[^1]

[^1]: Sidero Labs. The Architecture of Talos.
