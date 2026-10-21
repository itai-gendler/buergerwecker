---
kind: configuration
of: business-rule
takesEffect: The city catalog selects the rule when a polling cycle evaluates candidates. The selected seen keys travel with the digest to successful-delivery recording.
stability: A changed city policy applies to subsequent evaluations. Old recorded identities remain until seven-day retention removes them; switching identity spaces can make currently matching inventory new again.
alternatives:
- id: slot-identity
  selectedWhen: The city selects slot granularity, or says nothing and its booking system lists every free slot. An unknown configured value uses slot granularity.
- id: day-identity
  selectedWhen: The city selects day granularity, or says nothing and its booking system (TEVIS) shows only each office's earliest slot.
references:
- kind: code
  role: implementation
  target: app/catalog.py#_default_granularity
- kind: code
  role: implementation
  target: app/catalog.py#Catalog
- kind: code
  role: implementation
  target: app/cycle.py#_seen_key_fn
---

# Notification granularity

City configuration chooses whether changing times represent distinct inventory or a replacement earliest appointment.
