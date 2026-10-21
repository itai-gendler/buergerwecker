---
domain: subscriptions
references:
- kind: code
  role: implementation
  target: app/api.py#create_subscription
- kind: code
  role: implementation
  target: app/repo.py#insert_push_subscription
relations:
- entity: free-slot
  verb: provides access to
  cardinality: many-to-many
---

# App alert

A device-owned request to watch a service and receive push notifications. An alert provides access to the city’s ordinary availability, and to sensitive-service availability only for its own service; the access rule also requires an active term and a verified device.

## Information kept

- **City and office group** — The selected catalog tenant; one city can contain several office groups.
- **Appointment type** — The one offered service selected by the form.
- **Offices** — All offices or the selected offices in that tenant.
- **Weekdays** — The selected ISO weekdays, Monday through Sunday.
- **Time window** — Inclusive local start and end times.
- **Days ahead** — An optional positive calendar-day horizon measured from today in Europe/Berlin.
- **Language** — German or English stored with this alert.
- **End date** — The end of the term from creation or the latest renewal.
- **Last notified** — When a slot digest was last successfully delivered, initially absent.
- **Cadence** — Recent abundance and consecutive delivered digests used to space later notifications, initially unmeasured.
- **Check-in sent** — Whether the current term already received its still-looking question, initially no.
- **Legacy special consent** — Marks an existing sensitive-service alert; new sensitive-service alerts are not offered in the app.
- **Active** — Whether this non-ended alert is within its current term; device verification is a separate condition.

## States

### Active

Within its term; delivery also depends on device verification.

### Expired

Term ended; retained for renewal during the grace period.

### Ended

Stopped by the resident, delivery retirement or cleanup.
