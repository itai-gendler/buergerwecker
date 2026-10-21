---
entities:
- entity: free-slot
  shows:
  - City and office group
  - Office
  - Date
  - Time
  - Last checked
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

# Home-screen widget

Read the earliest matching opportunity for the cities of active alerts and open the app.
