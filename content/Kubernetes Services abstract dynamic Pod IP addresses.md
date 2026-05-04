publish: true
gemini: true
tags:
  - kubernetes
  - site_reliability
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact

# Kubernetes Services abstract dynamic Pod IP addresses

Because pods are ephemeral, their IP addresses change constantly. Services provide a stable, unchanging network endpoint that routes traffic to the underlying dynamic pods, proving that [[Separation of concerns improves maintainability]].[^1]

[^1]: Kubernetes Networking Model.
