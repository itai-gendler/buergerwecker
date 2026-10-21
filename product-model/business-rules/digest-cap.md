---
appliesTo:
- type: entity
  id: email-subscription
- type: entity
  id: app-alert
references:
- kind: code
  role: implementation
  target: app/cycle.py#subscriber_cap
- kind: code
  role: implementation
  target: app/repo.py#digests_in_window
- kind: code
  role: implementation
  target: app/digest.py#flush_digests
---

# Email and push share the same rolling digest limit

Each saved search normally receives at most two slot digests in any rolling 24 hours. At the configured mail-pool pressure threshold, normally 80 percent, the effective limit normally becomes one for both channels. Zero ordinary cap disables both ordinary and pressure caps; zero pressure cap or threshold disables tightening. Confirmation, management, check-in and heartbeat emails are separate from slot-digest counts.
