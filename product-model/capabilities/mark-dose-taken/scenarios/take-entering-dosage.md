---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Taken for a dose whose reminder asks for the dosage
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product opens the app and asks for the dosage, prefilled with the reminder's dosage
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Dosage, Asks for dosage]}
  contexts:
    app:
      place: android-app::dosage-entry
- text: The User enters the dosage taken and confirms
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Dosage]}
  contexts:
    app:
      place: android-app::dosage-entry
- text: The Product records the entered dosage, marks the event taken and reduces the stock by it
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Raised, to: Taken, facts: [Dosage, Taken or skipped time, Stock after]}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::dosage-entry
---

# Take a dose entering its dosage

## Trigger

The amount of a dose varies from day to day.

## Outcome

The event keeps the dosage actually taken.

## Edge cases

- Cancelling the prompt leaves the dose raised.
- In a combined notification the doses that do not ask are taken at once and each asking dose gets its own prompt.
