---
type: web
actors:
- resident
- operator
entryPoints:
- web: /
references:
- kind: code
  role: implementation
  target: app/web.py
---

# Website

The browser surface for email subscriptions, information and operator status.
