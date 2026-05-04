publish: true
gemini: true
tags:
  - kubernetes
  - site_reliability
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact

# Grafana alerting integrates metric thresholds with incident response

By setting mathematical thresholds in Grafana, the system can automatically page an SRE via PagerDuty if error budgets are consumed too quickly. This automation guarantees that [[Error budgets align dev and ops incentives]].[^1]

[^1]: Grafana Alerting Engine Mechanics.
