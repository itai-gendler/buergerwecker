---
availability:
- place: website::public
- place: website::subscription
- place: mobile-app::public
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/web.py#go_route
- kind: code
  role: implementation
  target: app/web.py#go_sub_route
- kind: code
  role: implementation
  target: app/catalog.py#booking_start_url
- kind: code
  role: implementation
  target: client/www/screens/city.js
- kind: code
  role: implementation
  target: client/www/app.js
---

# Open official booking site

Open the city’s current booking start page, resolved from the catalog when the link is followed. The resident completes the city’s own flow; no slot is booked or reserved by Bürgerwecker.
