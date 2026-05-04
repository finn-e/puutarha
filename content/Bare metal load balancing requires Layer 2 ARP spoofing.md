publish: true
gemini: true
tags:
  - kubernetes
  - site_reliability
created: '2026-05-04 14:40'
last_modified: '2026-05-04 14:40:00'
status: evergreen
confidence: fact

# Bare metal load balancing requires Layer 2 ARP spoofing

Unlike AWS, homelabs lack managed cloud load balancers. Exposing an IP to the local network requires tools like Cilium's BGP/L2 announcements or MetalLB to broadcast MAC addresses, solving the routing gap.[^1]

[^1]: Cilium L2 Announcement Documentation.
