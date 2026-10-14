---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Duplicate in the medicine menu
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicine
- text: The Product creates a copy of the medicine with the same tags and returns to the list
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: creates, facts: [Name, Icon, Notes, Color, Notification priority, Cannot be skipped, Stock amount, Unit, Refill size, Production date, Expiration date, Half-life, Time to peak, Position]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicines
---

# Duplicate a medicine

## Trigger

The User keeps a similar medicine.

## Outcome

A second medicine with the same details and tags but no reminders exists.
