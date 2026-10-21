---
appliesTo:
- type: capability
  id: view-earliest-slot-widget
- type: capability
  id: refresh-appointment-availability
references:
- kind: code
  role: implementation
  target: client/www/widget.js#buildConfig
- kind: code
  role: implementation
  target: client/ios/App/BuergerweckerWidget/BuergerweckerWidget.swift
- kind: code
  role: implementation
  target: client/android/app/src/main/java/de/buergerwecker/app/EarliestSlotWidget.java
---

# The widget shows only matching active-alert opportunities

The widget considers at most five cities of active alerts, excludes legacy sensitive-service alerts and respects every alert filter. It never presents a passed appointment as current. It opens the app when tapped and does not book.
