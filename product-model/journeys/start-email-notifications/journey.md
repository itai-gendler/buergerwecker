---
actors:
- resident
references:
- kind: code
  role: implementation
  target: app/web.py#subscribe
- kind: code
  role: implementation
  target: app/confirmations.py#build_confirmation
---

# Start email notifications

## Goal

Save an email search and activate it through its confirmation email.

## Success criterion

The saved search is confirmed and active.
