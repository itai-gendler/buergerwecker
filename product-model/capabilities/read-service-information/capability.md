---
availability:
- place: website::public
- place: mobile-app::public
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/templates/_parts.html
- kind: code
  role: implementation
  target: app/templates/datenschutz.html
- kind: code
  role: implementation
  target: app/templates/impressum.html
- kind: code
  role: implementation
  target: client/www/screens/settings.js
---

# Read service information

Read the FAQ, privacy notice and imprint on the website. The app opens the privacy notice, imprint and contact page from Settings. The privacy notice states the configured subscription and grace periods.
