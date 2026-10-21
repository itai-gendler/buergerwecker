---
acts: external
kind: person
relations:
- entity: email-subscription
  verb: holds
  cardinality: one-to-many
- entity: push-device
  verb: uses
  cardinality: one-to-many
- entity: retained-notification
  verb: keeps
  cardinality: one-to-many
references:
- kind: doc
  role: context
  target: README.md
- kind: doc
  role: context
  target: client/README.md
---

# Resident

A person looking for an appointment, using email links or their own phone; Bürgerwecker creates no user account. Holding an email subscription means presenting its valid action link for the requested operation; using a push device means acting through that installation’s device credential.

## Information kept

- **Preferred app language** — German or English, retained locally on this installation; initially derived from the phone language.
