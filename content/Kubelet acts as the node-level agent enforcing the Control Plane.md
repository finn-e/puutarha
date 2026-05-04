publish: true
gemini: true
tags:
  - kubernetes
  - systems_thinking
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact

# Kubelet acts as the node-level agent enforcing the Control Plane

Running on every worker node, the kubelet registers the server with the control plane and ensures that the containers described in the PodSpecs are actually running and healthy. It is the physical executor of the declarative system.[^1]

[^1]: Kubernetes Components: Kubelet.
