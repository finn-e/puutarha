publish: true
gemini: true
tags:
  - kubernetes
  - site_reliability
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: stable

# Ingress controllers route external HTTP traffic to internal Services

An Ingress controller acts as the single gateway for external traffic entering the cluster, reading URL paths and directing them to the correct internal service. It centralizes routing logic, preventing [[Local optimization often leads to global sub-optimization]].[^1]

[^1]: Kubernetes Documentation: Ingress.
