publish: true
gemini: true
tags:
  - kubernetes
  - software_engineering
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: stable

# StatefulSets provide stable network identities for databases

Unlike standard deployments, StatefulSets maintain a sticky identity for each of their pods, which is absolutely required for distributed databases to maintain quorum after a restart. They manage the data gravity that proves [[Persistent Volume migration is the hardest part of cluster upgrades]].[^1]

[^1]: Kubernetes Documentation: StatefulSets.
