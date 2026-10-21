---
availability:
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/api.py#city_slots
- kind: code
  role: implementation
  target: client/www/screens/city.js
- kind: code
  role: implementation
  target: client/www/state.js
---

# View city availability

Read the server’s last complete polls for watched services, including the soonest slots, total count and last-check time. This is available to a verified device with a live alert in that city while the mobile service is enabled.
