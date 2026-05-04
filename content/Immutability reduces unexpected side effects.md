---
publish: true
gemini: true
tags:
  - software_engineering
  - linux_philosophy
created: '2026-05-04 11:58'
last_modified: '2026-05-04 11:58:00'
status: evergreen
confidence: fact
---

# Immutability reduces unexpected side effects

If data structures cannot be altered after creation, an entire class of race conditions and synchronization bugs ceases to exist. While perfect for servers, [[Declarative OS configuration has limits for desktop use]] due to the friction it introduces.[^1]

[^1]: Goetz, B. (2006). Java Concurrency in Practice. Addison-Wesley.
