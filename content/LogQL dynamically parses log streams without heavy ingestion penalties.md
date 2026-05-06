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

# LogQL dynamically parses log streams without heavy ingestion penalties

Because Loki doesn't full-text index, LogQL uses regular expressions at query-time to filter and parse raw JSON logs. This delays the computational cost until the data is actually needed for debugging.[^1]

[^1]: LogQL: Log Query Language Documentation.
