publish: true
gemini: true
tags:
  - kubernetes
  - systems_thinking
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact

# Distributed tracing identifies latency bottlenecks in microservices

When a single user request bounces across fifteen microservices, standard logging cannot show which service took 500ms to reply. Tracing injects a unique ID that follows the request, pinpointing exactly where the failure occurred.[^1]

[^1]: CNCF OpenTelemetry Tracing Concepts.
