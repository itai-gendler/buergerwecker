---
references:
- kind: code
  role: implementation
  target: app/admin.py
- kind: code
  role: implementation
  target: app/templates/admin.html
---

# Delivery history

The operational history presented on the administration page.

## Information kept

- **Volume** — Delivered notifications and provider usage over the displayed windows.
- **Deferrals** — Counts, times and causes of deferred delivery, including hourly and daily quota waits.
- **Subscriber holds** — Subscriptions held by their rolling digest limit.
- **Feedback** — Delivery, bounce, complaint and unsubscribe totals and provider feedback status.
