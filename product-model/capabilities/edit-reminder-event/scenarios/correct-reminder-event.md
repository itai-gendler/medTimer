---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens a taken event and changes its name, dosage, notes or times
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Notes, Reminded time, Taken or skipped time]}
  contexts:
    app:
      place: android-app::edit-event
- text: The User closes the event
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::edit-event
- text: The Product keeps the changes and corrects the medicine stock by the difference in dosage
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, facts: [Medicine name, Dosage, Notes, Reminded time, Taken or skipped time, Stock after]}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::edit-event
---

# Correct an event

## Trigger

An event was recorded with the wrong details.

## Outcome

The event shows the corrected details and the stock matches them.

## Edge cases

- An additional dose has no reminder, so editing it changes no stock.
- Only the date of an additional dose can be changed; other events keep their date.
