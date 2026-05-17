---
title: Home Assistant Kubernetes DNS policy
aliases: ["ClusterFirstWithHostNet", "mDNS in Kubernetes"]
tags: ["kubernetes", "networking", "home-assistant"]
status: evergreen
confidence: stable
publish: true
gemini: true
created: 2026-05-17T10:50:00-04:00
last_modified: 2026-05-17T10:50:00-04:00
---

# Home Assistant Kubernetes DNS Policy

Home Assistant relies heavily on local network broadcast traffic (mDNS, UPnP) to automatically discover smart home devices. Kubernetes overlay networks (like Flannel or Cilium) block broadcast traffic from reaching the Pod.

To fix this, Home Assistant must be run with `hostNetwork: true`. However, doing this bypasses `kube-dns`. The Pod will no longer be able to resolve internal Kubernetes services.

**The Fix:** You must apply `dnsPolicy: ClusterFirstWithHostNet`. This instructs the Kubelet to route DNS queries back into the cluster's DNS provider, even though the Pod is operating directly on the node's physical network.[^1]

---
[^1]: Kubernetes Documentation, "DNS for Services and Pods".
