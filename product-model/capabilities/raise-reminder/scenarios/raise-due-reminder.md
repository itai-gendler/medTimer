---
kind: primary
routes:
  app: Android app
steps:
- text: An enabled time based reminder is due
  kind: condition
  unattended: true
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Time, Enabled, Weekdays, Days of month, First cycle start, Active days, Pause days, Active from, Active until]}
  - {entity: settings, effect: reads, facts: [Weekend mode, Weekend days, Weekend start time, Weekend end time]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product records a raised event with the medicine name, dosage, tags and stock, and the number of repeats
  kind: product
  entities:
  - {entity: reminder-event, effect: creates, to: Raised, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage]}
  - {entity: medicine, effect: reads, facts: [Name, Color, Icon, Cannot be skipped, Stock amount]}
  - {entity: settings, effect: reads, facts: [Number of repetitions]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product posts the reminder notification
  kind: product
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time, Tags, Stock after]}
  - {entity: time-based-reminder, effect: reads, facts: [Instructions]}
  - {entity: settings, effect: reads, facts: [Hide medication name in notification, Big notification buttons, Persistent reminders on lock screen]}
  contexts:
    app:
      place: android-app::reminder-notification
---

# Raise a due reminder

## Trigger

The reminder's time arrives on a day it is active.

## Outcome

The dose is raised in the Overview and its notification is shown.

## Decision points

### Combined notification

Are other reminders due at the same moment?

- Combine same time notifications is on → all due doses share one notification.
- It is off → each dose gets its own notification.

## Edge cases

- Without the notification permission the event is still raised, without a notification.
- Without exact reminders a reminder can come a few minutes late.
