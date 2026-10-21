---
availability:
- place: delivery-feedback
references:
- kind: code
  role: implementation
  target: app/web.py#webhook_route
- kind: code
  role: implementation
  target: app/webhooks.py#apply_events
- kind: code
  role: implementation
  target: app/repo.py#record_soft_bounce
---

# Apply delivery feedback

Accept delivery events from configured mail providers. Hard bounces and complaints stop all email subscriptions for the address; unsubscribe events stop them without suppressing future sign-ups.
