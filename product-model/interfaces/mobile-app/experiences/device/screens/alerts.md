---
entities:
- entity: app-alert
  shows:
  - City and office group
  - Appointment type
  - Offices
  - Weekdays
  - Time window
  - Days ahead
  - End date
- entity: free-slot
  shows:
  - City and office group
  - Appointment type
  - Office
  - Date
  - Time
  - Last checked
references:
- kind: code
  role: implementation
  target: client/www/screens/subs.js
---

# My alerts

Read saved alerts, matching slots and term end dates; edit, stop or keep looking.
