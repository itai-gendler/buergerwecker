---
appliesTo:
- type: entity
  id: email-subscription
- type: entity
  id: app-alert
- type: entity
  id: free-slot
references:
- kind: code
  role: implementation
  target: app/filters.py#matches
- kind: code
  role: implementation
  target: client/www/filters.js#matches
- kind: code
  role: implementation
  target: client/ios/App/BuergerweckerWidget/BuergerweckerWidget.swift
---

# Matching honors service, office, weekday and inclusive local times

A candidate must match the selected service and office set, its ISO weekday, and both inclusive time bounds. A days-ahead limit uses the current Europe/Berlin date; a slot outside that horizon is not marked seen and may qualify later.
