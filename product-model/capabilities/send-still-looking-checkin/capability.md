---
availability:
- place: website::subscription
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_send_renewal_reminders
- kind: code
  role: implementation
  target: app/housekeeping.py#_send_push_checkins
- kind: code
  role: implementation
  target: app/push.py#render_checkin
domain: subscriptions
---

# Send still-looking check-in

Send one check-in shortly before each active term ends, by email or push. Offer Keep looking and Stop; no reply lets the term expire.
