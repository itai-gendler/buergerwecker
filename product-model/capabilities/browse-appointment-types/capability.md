---
availability:
- place: website::public
- place: mobile-app::public
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/catalog.py
- kind: code
  role: implementation
  target: app/web.py#city_page
- kind: code
  role: implementation
  target: app/api.py#city
- kind: code
  role: implementation
  target: client/www/screens/city.js
---

# Browse appointment types

Read offered appointment types and relevant offices, with catalog names localized where translations exist. Excluded services are absent; the app additionally omits sensitive services.
