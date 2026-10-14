---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Taken on the reminder notification
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product marks the event taken now and reduces the medicine stock by the dosage
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Raised, to: Taken, facts: [Taken or skipped time, Stock after]}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product removes the dose from the notification and stops its repeats
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name]}
  contexts:
    app:
      place: android-app::reminder-notification
---

# Take a dose from its notification

## Trigger

A reminder notifies and the User takes the dose.

## Outcome

The event is taken; the stock is lower; the next reminder that depends on it is scheduled.

## Edge cases

- In a combined notification only the doses still open are taken; the notification disappears when none are left.
