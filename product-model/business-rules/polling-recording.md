---
appliesTo:
- type: capability
  id: refresh-appointment-availability
- type: capability
  id: detect-catalog-changes
- type: capability
  id: send-polling-alert
- type: capability
  id: send-backup-alert
- type: capability
  id: send-operations-summary
- type: entity
  id: polling-history
references:
- kind: code
  role: implementation
  target: app/admin.py
- kind: code
  role: implementation
  target: app/housekeeping.py
- kind: code
  role: implementation
  target: app/cycle.py
---

# Polling and maintenance contribute to polling history

Polling observations, failures, maintenance times, operational notices and catalog differences are available to the operator.
