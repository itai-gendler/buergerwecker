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
- type: capability
  id: apply-delivery-feedback
- type: entity
  id: delivery-history
references:
- kind: code
  role: implementation
  target: app/admin.py
- kind: code
  role: implementation
  target: app/digest.py#flush_digests
- kind: code
  role: implementation
  target: app/mail.py#send_batch
---

# Successful delivery and deferral contribute to delivery history

The operator’s history records delivered notifications, provider usage, quota deferrals, per-subscription holds and delivery feedback. Internal delivery receipts are not separate user-facing objects.
