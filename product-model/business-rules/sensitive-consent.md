---
appliesTo:
- type: capability
  id: subscribe-to-appointments
- type: capability
  id: edit-subscription
- type: entity
  id: email-subscription
  facts:
  - Special consent
references:
- kind: code
  role: implementation
  target: app/signup.py#build_filter
- kind: code
  role: implementation
  target: app/repo.py#set_special_consent
- kind: code
  role: implementation
  target: app/api.py#_filter_from_json
---

# Sensitive-service email selections require separate consent

Selecting an offered sensitive service requires explicit consent in addition to email confirmation. Editing back to an ordinary service clears that selection-specific consent. The app does not offer new sensitive-service selections.
