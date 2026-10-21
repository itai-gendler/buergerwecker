---
availability:
- place: website::subscription
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_clamp_expiry
- kind: code
  role: implementation
  target: app/config.py#ttl_days_for
domain: subscriptions
---

# Shorten subscription term

Apply a reduced configured term as a ceiling on remaining time for existing searches during housekeeping. Raising the term does not automatically renew them.
