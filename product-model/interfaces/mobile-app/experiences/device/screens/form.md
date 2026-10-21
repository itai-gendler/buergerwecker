---
entities:
- entity: app-alert
  collects:
  - City and office group
  - Appointment type
  - Offices
  - Weekdays
  - Time window
  - Days ahead
  - Language
references:
- kind: code
  role: implementation
  target: client/www/screens/form.js
---

# Alert settings

Choose a service and appointment filters for a new or existing alert.
