---
availability:
- place: mobile-app::public
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: client/www/app.js#act
- kind: code
  role: implementation
  target: client/www/screens/inbox.js#open
domain: notifications
---

# Follow retained notification

Open the context of a slot or check-in message. A push tap may open the official booking link; a retained list entry opens current app context.
