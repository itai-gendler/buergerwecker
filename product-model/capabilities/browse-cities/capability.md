---
availability:
- place: website::public
- place: mobile-app::public
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/web.py#index
- kind: code
  role: implementation
  target: app/web.py#_tenant_switcher
- kind: code
  role: implementation
  target: app/api.py#cities
- kind: code
  role: implementation
  target: client/www/screens/cities.js
---

# Browse cities

Find the supported city and distinguish its office groups. Unknown or unreadable catalog entries do not become a default city.
