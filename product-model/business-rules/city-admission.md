---
appliesTo:
- type: capability
  id: subscribe-to-appointments
- type: capability
  id: confirm-email-subscription
- type: capability
  id: edit-subscription
- type: capability
  id: renew-subscription
references:
- kind: code
  role: implementation
  target: app/planning.py#cap_refuses
- kind: code
  role: implementation
  target: app/api.py#_share_refusal
- kind: code
  role: implementation
  target: app/web.py#confirm_route
---

# City capacity distinguishes mail-held and app-held services

Capacity counts distinct watched services after office variants can be collapsed. Mail may join an already-polled service; adding a new one is judged against mail-held services plus app-only excess beyond half the city cap. App-only service ownership is limited to half the cap, rounded down; joining a mail-held service does not use that app-only share. App creation and renewal also obey at most three non-ended alerts per device per city, including expired-but-renewable alerts, and a configurable city-wide app ceiling, normally 100; creation, editing and renewal obey at most three distinct services per device per city. Editing leaves out the request being replaced. Renewal repeats current admission without invalidating a term already running.
