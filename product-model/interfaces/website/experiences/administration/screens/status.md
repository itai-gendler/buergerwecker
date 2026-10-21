---
entities:
- entity: delivery-history
  shows:
  - Volume
  - Deferrals
  - Subscriber holds
  - Feedback
- entity: polling-history
  shows:
  - Latest poll
  - Failures
  - Catalog differences
  - Maintenance
- entity: service-settings
  shows:
  - Digest limit
  - Pressure limit
references:
- kind: code
  role: implementation
  target: app/templates/admin.html
- kind: code
  role: implementation
  target: app/admin.py
entryPoints:
- website: /admin
---

# Service status

Read subscription totals, delivery quotas, deferrals, availability history and maintenance health.
