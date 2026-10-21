---
appliesTo:
- type: capability
  id: open-booking-site
- type: capability
  id: send-appointment-notifications
- type: capability
  id: view-city-availability
references:
- kind: code
  role: implementation
  target: app/web.py#go_route
- kind: code
  role: implementation
  target: client/www/screens/city.js
---

# Appointments are booked only on the official city site

Bürgerwecker reports availability and provides the city’s booking start page. It never reserves an appointment or completes a booking for the resident.
