---
references:
- kind: code
  role: implementation
  target: app/models.py#Slot
- kind: code
  role: implementation
  target: app/snapshots.py#record_snapshots
---

# Free slot

An observed appointment opportunity on an official booking site; observing it does not reserve it.

## Information kept

- **City and office group** — The catalog tenant being watched.
- **Appointment type** — The service whose poll found the opportunity.
- **Office** — The office offering it.
- **Date** — The appointment date in the city.
- **Time** — The appointment time in the city.
- **Last checked** — When the complete service poll produced this observation.
