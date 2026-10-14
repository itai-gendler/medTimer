---
kind: primary
routes:
  app: Android app
steps:
- text: A dose is still raised the time between repetitions after its notification, with repeats left
  kind: condition
  unattended: true
  entities:
  - {entity: reminder-event, effect: reads, facts: [Remaining repeats]}
  - {entity: settings, effect: reads, facts: [Repeat reminders, Time between repetitions]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product notifies the dose again and counts one repeat off
  kind: product
  entities:
  - {entity: reminder-event, effect: changes, facts: [Remaining repeats]}
  contexts:
    app:
      place: android-app::reminder-notification
---

# Repeat an unanswered reminder

## Trigger

The User has not answered a reminder.

## Outcome

The notification comes again until the dose is answered or no repeats remain.
