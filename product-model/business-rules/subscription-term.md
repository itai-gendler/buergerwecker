---
appliesTo:
- type: entity
  id: email-subscription
  facts:
  - End date
- type: entity
  id: app-alert
  facts:
  - End date
references:
- kind: code
  role: implementation
  target: app/config.py#ttl_days_for
- kind: code
  role: implementation
  target: app/repo.py#insert_pending
- kind: code
  role: implementation
  target: app/repo.py#renew_subscription
- kind: code
  role: implementation
  target: app/housekeeping.py#_clamp_expiry
---

# Subscription terms start at sign-up or renewal

Confirmation preserves the term saved at sign-up. Renewal sets a new end date from now. The sensitive term is the smaller of its configured term and the ordinary term; it never exceeds the ordinary term. Lower configuration ceilings can shorten existing terms; raising them does not extend a term without renewal.
