---
kind: validation
routes:
  app: Android app
steps:
- text: The medicine of the dose cannot be skipped
  kind: condition
  entities:
  - {entity: reminder-event, effect: reads, facts: [Cannot be skipped]}
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The User swipes the reminder notification away while its dismiss action is Skip dose
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product snoozes the dose instead of skipping it; the notification, alarm, Overview and event offer no Skipped for it
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Cannot be skipped]}
  - {entity: settings, effect: reads, facts: [Action when dismissing notification, Snooze duration]}
  contexts:
    app:
      place: android-app::reminder-notification
---

# A dose that cannot be skipped

## Trigger

A reminder notifies for a medicine marked Medicine cannot be skipped.

## Outcome

The dose stays open until it is taken.
