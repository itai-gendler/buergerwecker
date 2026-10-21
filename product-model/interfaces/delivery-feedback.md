---
type: webhook
actors:
- mail-provider
entryPoints:
- webhook: /webhooks/<provider>/<secret>
references:
- kind: code
  role: implementation
  target: app/webhooks.py
---

# Delivery feedback

The inbound contract through which configured mail providers report delivery outcomes.
