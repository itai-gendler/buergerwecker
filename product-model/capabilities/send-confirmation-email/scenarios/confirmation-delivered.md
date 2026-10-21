---
kind: primary
routes:
  public: Public
  link: Link
steps:
- text: The confirmation sweep finds an eligible pending sign-up and mail-pool room.
  kind: condition
  entities: []
  contexts:
    public:
      place: website::public::signup
    link:
      place: website::subscription
  unattended: true
- text: The Product sends the confirmation link and marks the email subscription as having received it.
  kind: product
  entities:
  - entity: email-subscription
    effect: changes
    facts:
    - Confirmation sent
  contexts:
    public:
      place: website::public::signup
    link:
      place: website::subscription
---

# Deliver a saved sign-up’s confirmation

## Trigger

The confirmation sweep finds an eligible pending sign-up and mail-pool room.

## Outcome

The Product sends the confirmation link and marks the email subscription as having received it.

## Edge cases

- No appointment alert is sent until confirmation.
- The delivery key is stable for the saved sign-up across retries.
