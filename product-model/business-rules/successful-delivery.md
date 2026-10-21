---
appliesTo:
- type: capability
  id: send-appointment-notifications
- type: capability
  id: send-confirmation-email
- type: capability
  id: send-still-looking-checkin
references:
- kind: code
  role: implementation
  target: app/digest.py#flush_digests
- kind: code
  role: implementation
  target: app/confirmations.py#send_pending_confirmations
- kind: code
  role: implementation
  target: app/housekeeping.py
---

# Only successful delivery marks opportunities reported

Deduplication history, last-notified time, cadence measurements and rolling digest counts advance only for successfully delivered digests. Deferred or failed messages leave candidate opportunities eligible for fresh evaluation.
