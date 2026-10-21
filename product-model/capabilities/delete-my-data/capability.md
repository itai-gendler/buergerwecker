---
availability:
- place: mobile-app::public
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: client/www/screens/settings.js
- kind: code
  role: implementation
  target: client/www/push.js#deleteEverything
- kind: code
  role: implementation
  target: app/api.py#device_delete
- kind: code
  role: implementation
  target: app/repo.py#delete_device
domain: settings
---

# Delete my data

Remove this phone’s server registration and its alerts, then clear retained local app data and notifications. Keep the selected language and return to onboarding.
