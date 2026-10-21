---
domain: subscriptions
references:
- kind: code
  role: implementation
  target: app/repo.py#insert_pending
- kind: code
  role: implementation
  target: app/web.py#confirm_route
- kind: code
  role: implementation
  target: app/housekeeping.py
---

# Email subscription

A request to watch an appointment selection and notify an email address.

## Information kept

- **Email address** — The normalized address used for confirmation and subsequent email.
- **City and office group** — The selected catalog tenant; one city can contain several office groups.
- **Appointment type** — The one offered service selected by the form.
- **Offices** — All offices or the selected offices in that tenant.
- **Weekdays** — The selected ISO weekdays, Monday through Sunday.
- **Time window** — Inclusive local start and end times.
- **Days ahead** — An optional positive calendar-day horizon measured from today in Europe/Berlin.
- **Language** — German or English, selected at sign-up.
- **End date** — The term starts when the sign-up is saved; confirmation does not restart it.
- **Last notified** — When a slot digest was last successfully delivered, initially absent.
- **Cadence** — Recent abundance and consecutive delivered digests used to space later notifications, initially unmeasured.
- **Check-in sent** — Whether the current term already received its still-looking question, initially no.
- **Special consent** — Whether and when separate consent was given for the selected sensitive service.
- **Confirmation sent** — Whether a confirmation email has been delivered, initially no.

## States

### Pending

Saved, awaiting confirmation.

### Active

Confirmed and within its term.

### Expired

Its term ended. Previously confirmed requests remain renewable during grace; an unconfirmed request requires a new sign-up.

### Ended

Unsubscribed or ended after the grace period; no further notifications.
