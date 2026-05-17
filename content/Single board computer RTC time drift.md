---
title: Single board computer RTC time drift
aliases: ["TLS time traveler error", "Raspberry Pi x509 future time"]
tags: ["hardware", "raspberry-pi", "tls", "networking"]
status: evergreen
confidence: fact
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Single Board Computer RTC Time Drift

Raspberry Pis lack an onboard Real-Time Clock (RTC) battery. When power is lost, the hardware defaults to the UNIX epoch upon boot until the NTP daemon syncs.[^1]

## The TLS Race Condition
During fresh OS installations, the API server may generate initial TLS certificates exactly as the NTP daemon corrects the clock. This can result in a certificate minted slightly *in the future* relative to the connecting client.

The client will throw an `x509: certificate has expired or is not yet valid` error.

## The Fix
Wait. Once the client's local clock ticks past the certificate's future mint timestamp, the connection will naturally succeed.

---
[^1]: Raspberry Pi Foundation, "Raspberry Pi Hardware Specifications".
