---
availability:
- place: website::administration
references:
- kind: code
  role: implementation
  target: app/mail.py#maybe_quota_alert
---

# Send quota alert

Notify the operator when combined rolling daily mail usage crosses the configured warning line or mail is deferred for quota, normally at most once per day.
