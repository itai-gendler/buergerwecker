---
availability:
- place: website::subscription
references:
- kind: code
  role: implementation
  target: app/web.py#confirm_route
- kind: code
  role: implementation
  target: app/repo.py#confirm
- kind: code
  role: implementation
  target: app/web.py#_send_manage_link_email
domain: subscriptions
---

# Confirm email subscription

Activate a saved email request using its confirmation link. Confirmation preserves the original term and is successful even if the convenience management email cannot be sent.
