---
kind: primary
routes:
  app: Android app
steps:
- text: Location-based snooze is on and a home location is set
  kind: condition
  entities:
  - {entity: settings, effect: reads, facts: [Location-based snooze, Home location]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The User chooses Snooze until home on the reminder notification
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product removes the notification and watches for the arrival at home
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: changes, from: Raised, to: Snoozed until home, facts: []}
  - {entity: settings, effect: reads, facts: [Home location]}
  contexts:
    app:
      place: android-app::reminder-notification
---

# Snooze until arriving home

## Trigger

The User is away from the medicine.

## Outcome

The Overview shows the dose as snoozed until home; it notifies again on arrival.

## Edge cases

- Taking or skipping the dose meanwhile ends the snooze.
