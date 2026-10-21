---
singleton: true
references:
- kind: code
  role: implementation
  target: app/config.py
- kind: code
  role: implementation
  target: app/housekeeping.py
---

# Service settings

Deployment configuration controlling availability, notification budgets and retention.

## Information kept

- **App available** — Whether the mobile service is enabled.
- **Ordinary term** — Configured days for ordinary subscriptions.
- **Sensitive term** — Configured ceiling for sensitive-service subscriptions, bounded by the ordinary term.
- **Grace period** — Configured days after expiry during which renewal remains possible.
- **Digest limit** — Configured per-subscription rolling-24-hour maximum, normally two; zero disables it.
- **Pressure threshold** — Configured percentage of the combined rolling mail pool that tightens the limit.
- **Pressure limit** — The reduced limit for both channels while mail-pool pressure lasts.
- **Feedback enabled** — Whether delivery-feedback processing is configured.
- **Catalog comparison enabled** — Whether daily comparison with upstream catalogs is enabled.
