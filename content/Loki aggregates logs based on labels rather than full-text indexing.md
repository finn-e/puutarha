publish: true
gemini: true
tags:
  - kubernetes
  - site_reliability
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: stable

# Loki aggregates logs based on labels rather than full-text indexing

Traditional loggers like Elasticsearch index every single word, creating massive storage overhead. Loki only indexes the metadata labels (like pod name), making it drastically cheaper and faster to run on homelabs.[^1]

[^1]: Grafana Loki Architecture.
