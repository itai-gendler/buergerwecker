---
appliesTo:
- type: entity
  id: email-subscription
- type: entity
  id: app-alert
references:
- kind: code
  role: implementation
  target: app/cycle.py#run_cycle
- kind: code
  role: implementation
  target: app/digest.py#_behind_the_mail_wall
- kind: code
  role: implementation
  target: app/push.py#send_push_batch
---

# The longest-waiting searches lead delivery

Never-notified searches come first, then the oldest last-notified time. Hourly mail quota exhaustion holds later push candidates behind the first quota-deferred mail candidate. A binding daily mail limit or a provider outage does not impose that push hold. Push cycle budgets do not hold mail.
