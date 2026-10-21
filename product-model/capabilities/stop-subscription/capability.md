---
availability:
- place: website::subscription
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/web.py#unsubscribe_route
- kind: code
  role: implementation
  target: app/api.py#delete_subscription
- kind: code
  role: implementation
  target: client/www/screens/subs.js
domain: subscriptions
---

# Stop subscription

End a saved search. Web unsubscribe first presents a confirmation; posting it ends the request. Mobile Stop and No, I have got one end the selected alert.
