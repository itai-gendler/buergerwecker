---
appliesTo:
- type: entity
  id: free-slot
- type: capability
  id: send-appointment-notifications
references:
- kind: code
  role: implementation
  target: app/cycle.py#run_cycle
- kind: code
  role: implementation
  target: app/digest.py#render_digest_text
---

# Notifications examine the earliest fifty matching opportunities

Each search considers only its earliest 50 matching logical slots before filtering already-reported ones. Slots beyond this horizon remain unreported; the cycle does not page through batches of unseen later inventory. Email shows at most 25 candidate lines and a remaining count; all delivered candidates within the horizon are recorded as reported.
