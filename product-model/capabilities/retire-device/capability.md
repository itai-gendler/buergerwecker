---
availability:
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/push.py#send_push_batch
- kind: code
  role: implementation
  target: app/repo.py#retire_device
---

# Retire device

Retire a destination established as dead by its push relay and end its alerts. A platform-wide delivery failure alone leaves registrations intact.
