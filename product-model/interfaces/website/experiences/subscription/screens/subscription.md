---
entities:
- entity: email-subscription
  shows:
  - City and office group
  - Appointment type
  - Offices
  - Weekdays
  - Time window
  - Days ahead
  - End date
  - Special consent
  collects:
  - Appointment type
  - Offices
  - Weekdays
  - Time window
  - Days ahead
  - Special consent
references:
- kind: code
  role: implementation
  target: app/templates/manage.html
- kind: code
  role: implementation
  target: app/web.py
entryPoints:
- website: /manage/<token>
---

# Your subscription

Confirm, inspect, edit, renew or stop the subscription addressed by an email link.
