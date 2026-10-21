---
appliesTo:
- type: capability
  id: send-appointment-notifications
- type: capability
  id: send-confirmation-email
- type: capability
  id: send-still-looking-checkin
- type: capability
  id: send-no-match-heartbeat
references:
- kind: code
  role: implementation
  target: app/mail.py#_providers
- kind: code
  role: implementation
  target: app/mail.py#send_batch
- kind: code
  role: implementation
  target: app/confirmations.py#confirmation_room
---

# Batch delivery honors provider order and rolling capacity

Confirmation, digest, check-in and heartbeat batches use the configured provider chain and available rolling headroom. Hourly and daily windows apply where configured. The confirmation queue stops at its configured pressure line. Deferred appointment candidates are rebuilt from later polls.
