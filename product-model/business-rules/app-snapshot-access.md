---
appliesTo:
- type: capability
  id: view-city-availability
- type: capability
  id: view-earliest-slot-widget
references:
- kind: code
  role: implementation
  target: app/api.py#city_slots
---

# City snapshots belong to verified devices watching that city

Reading a city’s appointment observations requires a verified device with a non-ended, unexpired alert there. Sensitive-service observations additionally require the device’s own live alert for that service. App and widget share the 60-reads-per-hour device allowance.
