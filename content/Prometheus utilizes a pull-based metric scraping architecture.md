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
confidence: fact
---
=======
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact
>>>>>>> origin/trunk

# Prometheus utilizes a pull-based metric scraping architecture

Instead of applications pushing their health data to a central server, Prometheus reaches out and scrapes the `/metrics` endpoint of every pod. This decentralized approach prevents the monitoring system from being DDOSed by its own clients.[^1]

[^1]: Prometheus Architecture and Design.
