---
appliesTo:
- {type: entity, id: reminder-event, effect: changes, to: Taken}
permits:
- actors:
  - user
- unattended: true
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/ReminderNotificationProcessor.kt#ReminderNotificationProcessor
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/NotificationProcessor.kt#NotificationProcessor
---

# A raised dose is taken by the User, or by the Product when its reminder takes it automatically

A dose becomes taken when the User marks it so; the Product marks a dose taken on its own only for a reminder set to Automatically mark as taken.
