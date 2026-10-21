---
availability:
- place: website::subscription
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_send_heartbeats
- kind: code
  role: implementation
  target: app/housekeeping.py#_heartbeat_mail
domain: subscriptions
---

# Send no-match heartbeat

Tell a continuing email subscriber what a long period without notifications means, with links to edit the filter or unsubscribe. Milestones are 30 and 60 days and apply only while the subscription remains active.
