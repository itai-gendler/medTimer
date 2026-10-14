---
entities:
- {entity: reminder-event, shows: [Medicine name, Dosage, Reminded time, Tags, Stock after]}
- {entity: time-based-reminder, shows: [Instructions]}
- {entity: linked-reminder, shows: [Instructions]}
- {entity: interval-reminder, shows: [Instructions]}
- {entity: windowed-interval-reminder, shows: [Instructions]}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/ReminderNotificationFactory.kt#ReminderNotificationFactory
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/NotificationIntentBuilder.kt#NotificationIntentBuilder
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/NotificationStringBuilder.kt
---

# Reminder notification

The notification of a due dose, or of several due at the same time when they are combined: the medicine, dosage, time, instructions, tags and remaining stock, with Taken, Skipped, Snooze and Snooze until home as the settings allow. Dismissing it performs the action chosen in the notification settings.
