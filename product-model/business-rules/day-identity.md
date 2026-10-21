---
appliesTo:
- type: entity
  id: free-slot
- type: capability
  id: send-appointment-notifications
references:
- kind: code
  role: implementation
  target: app/catalog.py#Catalog
- kind: code
  role: implementation
  target: app/repo.py#has_seen_slot
- kind: code
  role: implementation
  target: app/housekeeping.py#_prune_seen_slots
---

# Day-granularity notifications report earlier openings as new

Under day granularity, date, office and service identify the opportunity, with the earliest reported time remembered. An equal or later time stays quiet; a strictly earlier time is new. Seen history is retained for seven days.
