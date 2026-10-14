---
kind: alternative
routes:
  app: Android app
steps:
- text: The User switches Enter dosage when taken or Automatically mark as taken, or picks the notification priority
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Enter dosage when taken, Automatically mark as taken, Notification priority]}
  contexts:
    app:
      place: android-app::reminder-settings
- text: The Product keeps the choices
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: changes, facts: [Enter dosage when taken, Automatically mark as taken, Notification priority]}
  contexts:
    app:
      place: android-app::reminder-settings
---

# Change dosage entry, automatic taking or priority

## Trigger

The dose varies, is only tracked for stock, or needs a different priority.

## Outcome

Later reminders ask for the dosage, are taken without a notification, or notify with the chosen priority.
