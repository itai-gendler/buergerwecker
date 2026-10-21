---
availability:
- place: mobile-app::public
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: client/www/screens/settings.js
- kind: code
  role: implementation
  target: client/www/i18n.js
- kind: code
  role: implementation
  target: app/repo.py#update_device
domain: settings
---

# Change language settings

Choose German or English for the app and its widget. First launch chooses from the device language. The app saves the preference locally and reports it to the registered device.
