---
kind: edge
routes:
  email: Email
  app: App
steps:
- text: A poll finds only matching opportunities already reported under the city’s deduplication policy.
  kind: condition
  entities: []
  contexts:
    email:
      place: website::subscription
    app:
      place: mobile-app::device
  unattended: true
- text: No notification is sent.
  kind: product
  entities: []
  contexts:
    email:
      place: website::subscription
    app:
      place: mobile-app::device
---

# Stay quiet about reported inventory

## Trigger

A poll finds only matching opportunities already reported under the city’s deduplication policy.

## Outcome

No notification is sent.
