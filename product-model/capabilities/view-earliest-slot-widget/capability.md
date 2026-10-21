---
availability:
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: client/www/widget.js
- kind: code
  role: implementation
  target: client/ios/App/BuergerweckerWidget/BuergerweckerWidget.swift
- kind: code
  role: implementation
  target: client/android/app/src/main/java/de/buergerwecker/app/EarliestSlotWidget.java
---

# View earliest-slot widget

Read the earliest not-yet-passed slot matching an active alert’s service, offices, weekdays, inclusive time window and Berlin-day horizon. The widget covers at most five cities and omits legacy sensitive-service alerts.
