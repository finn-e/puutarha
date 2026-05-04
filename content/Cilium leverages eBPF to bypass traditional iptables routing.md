publish: true
gemini: true
tags:
  - kubernetes
  - systems_thinking
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact

# Cilium leverages eBPF to bypass traditional iptables routing

Legacy Kubernetes networking relies on cascading chains of iptables rules, which degrade in performance as clusters scale. Cilium uses eBPF hash tables to route packets instantly, proving how [[Bottlenecks determine the throughput of a system]].[^1]

[^1]: Cilium Architecture Overview.
