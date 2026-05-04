publish: true
gemini: true
tags:
  - kubernetes
  - software_engineering
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact

# Time-series databases optimize for massive append-only workloads

Unlike relational SQL databases, TSDBs like Prometheus are designed strictly for high-velocity, timestamped metric ingestion. They sacrifice update capabilities for read/write speed, demonstrating how [[Constraints breed creative solutions]].[^1]

[^1]: Time Series Database Architectural Patterns.
