---
references:
- kind: code
  role: implementation
  target: app/repo.py#suppress_address
- kind: code
  role: implementation
  target: app/webhooks.py#apply_events
- kind: code
  role: implementation
  target: app/mail.py#_dead_addresses
---

# Email delivery

The delivery standing of an email address, shared by all subscriptions for that address.

## Information kept

- **Address** — The email address to which the standing applies.
- **Block reason** — Complaint, permanent bounce, repeated temporary bounces or repeated delivery rejection.
- **Temporary failures** — The count of consecutive temporary bounces.
- **Blocked since** — When suppression began.

## States

### Reachable

No active block on sending; temporary failures may be accumulating.

### Blocked

Messages to the address are suppressed.
