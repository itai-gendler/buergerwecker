---
appliesTo:
- type: entity
  id: resident
  effect: changes
  facts:
  - Preferred app language
permits:
- self: true
references:
- kind: code
  role: implementation
  target: client/www/screens/settings.js
---

# Residents change their own app language

The local language preference belongs to the person using this installation.
