---
appliesTo:
- type: entity
  id: free-slot
- type: capability
  id: send-appointment-notifications
references:
- kind: code
  role: implementation
  target: app/models.py#Slot
- kind: code
  role: implementation
  target: app/repo.py#has_seen_slot
- kind: code
  role: implementation
  target: app/housekeeping.py#_prune_seen_slots
---

# Slot-granularity notifications distinguish date, time, office and service

Under slot granularity, those four appointment facts identify an already-reported opportunity. Different counters and changing booking-session details do not create new notification opportunities. Seen history is retained for seven days.
