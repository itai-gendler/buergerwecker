---
kind: edge
routes:
  public: Public
  link: Link
steps:
- text: The pending-confirmation queue reaches the configured pressure line or providers cannot deliver.
  kind: condition
  entities: []
  contexts:
    public:
      place: website::public::signup
    link:
      place: website::subscription
  unattended: true
- text: The saved requests remain pending; later sweeps retry eligible requests without a second sign-up.
  kind: product
  entities: []
  contexts:
    public:
      place: website::public::signup
    link:
      place: website::subscription
---

# Wait for mail-pool room

## Trigger

The pending-confirmation queue reaches the configured pressure line or providers cannot deliver.

## Outcome

The saved requests remain pending; later sweeps retry eligible requests without a second sign-up.

## Edge cases

- Requests older than seven days are no longer retried for confirmation mail.
- An address that cannot be mailed does not occupy the front of the confirmation queue.
