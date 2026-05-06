<<<<<<< HEAD
---
=======
>>>>>>> origin/trunk
publish: true
gemini: true
tags:
  - kubernetes
  - systems_thinking
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

# Control loops continuously reconcile desired and actual states

Kubernetes is essentially a collection of infinite loops checking if the current state of the world matches the user's YAML definition. If a node dies, the loop detects the variance and spins up replacement pods elsewhere, utilizing how [[Feedback loops drive system behavior]].[^1]

[^1]: Kubernetes Architecture: Controller Pattern.
