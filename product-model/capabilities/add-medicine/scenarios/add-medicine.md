---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Add medicine and enters the medicine name
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicines
- text: The Product creates the medicine at the end of the list without stock, reminders or tags
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: creates, facts: [Name, Icon, Notes, Color, Notification priority, Cannot be skipped, Stock amount, Unit, Refill size, Production date, Expiration date, Half-life, Time to peak, Position]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicines
- text: The Product opens the new medicine
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicine
---

# Add a medicine

## Trigger

The User starts taking a new medicine.

## Outcome

The medicine exists with the entered name and its details are open, ready for reminders.

## Edge cases

- Cancelling the name prompt creates nothing.
