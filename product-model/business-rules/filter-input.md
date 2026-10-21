---
appliesTo:
- type: capability
  id: subscribe-to-appointments
- type: capability
  id: edit-subscription
references:
- kind: code
  role: implementation
  target: app/signup.py#build_filter
- kind: code
  role: implementation
  target: app/signup.py#parse_max_days
- kind: code
  role: implementation
  target: app/templates/_fields.html
- kind: code
  role: implementation
  target: client/www/screens/form.js
---

# Saved filters use offered catalog values and a nonempty time window

One offered service is required. Offices must belong to the tenant catalog. An empty office selection at the shared parser means all offices; an empty valid-weekday set means all seven days. Missing time bounds mean 00:00–23:59; reversed or invalid times are refused. A positive horizon up to 9999 days is accepted; blank, zero or invalid values mean no limit. User forms offer 3, 7, 14, 30 days and no limit, preserving other saved positive values.
