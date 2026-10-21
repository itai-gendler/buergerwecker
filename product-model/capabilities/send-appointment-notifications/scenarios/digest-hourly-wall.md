---
kind: edge
routes:
  email: Email
  app: App
steps:
- text: The cycle's email and push notifications stand in one queue, longest-waiting search first.
  kind: condition
  entities: []
  contexts:
    email:
      place: website::subscription
    app:
      place: mobile-app::device
  unattended: true
- text: The hourly mail quota runs out partway down that queue.
  kind: condition
  entities: []
  contexts:
    email:
      place: website::subscription
    app:
      place: mobile-app::device
- text: The Product delivers the email and push notifications ahead of the first email the quota turns away, and records them as delivered.
  kind: product
  entities:
  - entity: email-subscription
    effect: changes
    facts:
    - Last notified
    - Cadence
  - entity: app-alert
    effect: changes
    facts:
    - Last notified
    - Cadence
  contexts:
    email:
      place: website::subscription
    app:
      place: mobile-app::device
- text: That email, every email behind it and every push notification behind it wait, with nothing recorded as reported.
  kind: product
  entities: []
  contexts:
    email:
      place: website::subscription
    app:
      place: mobile-app::device
- text: On the next cycle the waiting searches lead the queue, still longest-waiting first, and are evaluated against the new poll.
  kind: product
  entities: []
  contexts:
    email:
      place: website::subscription
    app:
      place: mobile-app::device
---

# Keep one queue at the hourly mail limit

## Trigger

The hourly mail quota runs out partway through a cycle's queue of email and push notifications.

## Outcome

Push notifications behind the first deferred email wait with it, so neither channel gets ahead of searches that have waited longer; those ahead are delivered.

## Edge cases

- A binding daily mail limit does not impose this push hold.
- A mail-provider outage does not impose this quota hold.
- A push budget limit does not hold back mail.
