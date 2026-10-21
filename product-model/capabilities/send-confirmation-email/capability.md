---
availability:
- place: website::public
- place: website::subscription
references:
- kind: code
  role: implementation
  target: app/confirmations.py
- kind: code
  role: implementation
  target: app/repo.py#pending_confirmations
- kind: code
  role: implementation
  target: app/poller.py#_send_confirmations
domain: subscriptions
---

# Send confirmation email

Send unsent pending sign-up confirmations oldest first after slot-digest processing. Keep deferred sign-ups pending within a seven-day confirmation retry window.
