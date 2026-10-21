---
entities:
- entity: email-subscription
  collects:
  - Email address
  - City and office group
  - Appointment type
  - Offices
  - Weekdays
  - Time window
  - Days ahead
  - Language
  - Special consent
references:
- kind: code
  role: implementation
  target: app/templates/form.html
- kind: code
  role: implementation
  target: app/templates/_fields.html
entryPoints:
- website: /<city>
---

# Appointment notifications

Choose an appointment type, offices and filters and request email notifications.
