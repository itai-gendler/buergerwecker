---
availability:
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/snapshots.py#prune_snapshots
- kind: code
  role: implementation
  target: app/housekeeping.py#_prune_slot_snapshots
---

# Remove old appointment observations

Remove server-side appointment snapshots older than 24 hours during housekeeping, including snapshots of services no longer polled.
