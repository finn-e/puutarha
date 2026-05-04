---
publish: true
gemini: true
tags:
  - site_reliability
  - systems_thinking
created: '2026-05-04 11:58'
last_modified: '2026-05-04 11:58:00'
status: evergreen
confidence: fact
---

# Graceful degradation prioritizes core functionality

When a microservice fails, the overall application should disable non-critical features rather than crashing entirely. Designing for partial failure acknowledges that [[Complex systems exhibit emergent properties]] under stress.

[^1]: Nygard, M. T. (2007). Release It!. Pragmatic Bookshelf.
