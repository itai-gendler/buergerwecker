---
relations:
- entity: app-alert
  verb: owns
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: app/repo.py#register_device
- kind: code
  role: implementation
  target: app/repo.py#update_device
- kind: code
  role: implementation
  target: app/repo.py#retire_device
---

# Push device

The registered phone installation that owns app alerts.

## Information kept

- **Platform** — iPhone or Android push delivery.
- **Language** — The language reported by the installation.
- **Push destination** — The current platform notification destination.
- **Verification** — Whether a setup push to that destination has been acknowledged.
- **Last activity** — The latest recorded activity for retention purposes.

## States

### Unverified

Registered and waiting for the setup push to be acknowledged.

### Verified

The current push destination has completed setup.

### Retired

Delivery has established that this destination is no longer usable.
