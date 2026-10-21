---
availability:
- place: website::administration
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_check_backup_health
---

# Send backup alert

Notify the operator when the recorded backup time is absent or more than 48 hours old, or the backup reports a failure.
