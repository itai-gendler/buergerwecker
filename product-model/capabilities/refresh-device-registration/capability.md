---
availability:
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: client/www/push.js#onToken
- kind: code
  role: implementation
  target: app/api.py#device_update
- kind: code
  role: implementation
  target: app/repo.py#update_device
---

# Refresh device registration

Keep an existing installation registered when the platform changes its push destination or when the app reconnects after losing its registration.
