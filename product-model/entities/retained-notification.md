---
domain: notifications
references:
- kind: code
  role: implementation
  target: client/www/inbox.js
- kind: code
  role: implementation
  target: client/www/screens/inbox.js
---

# Retained notification

A slot or check-in notification retained on this phone for reading again.

## Information kept

- **Kind** — Slot availability or a still-looking check-in.
- **Text** — The notification title and body, when available.
- **Received time** — The original send or post time when supplied; otherwise the first time the app saw it.
- **Destination** — The related alert and, when present, city.
- **Read status** — New since the list was last opened, or already read.

## States

### Unread

Added since the last opening of the list.

### Read

The list has been opened since this entry arrived.
