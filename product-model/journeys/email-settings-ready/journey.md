---
actors:
- resident
references:
- kind: code
  role: implementation
  target: app/web.py#confirm_route
- kind: code
  role: implementation
  target: app/web.py#_send_manage_link_email
- kind: code
  role: implementation
  target: app/web.py#manage_route
---

# Confirm and reach email settings

## Goal

The resident follows the emailed confirmation for a saved request.

## Success criterion

The email subscription is active and its management-link destination shows the saved preferences.
