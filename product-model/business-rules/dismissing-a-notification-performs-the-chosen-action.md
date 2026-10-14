---
appliesTo:
- {type: capability, id: skip-dose}
- {type: capability, id: snooze-reminder}
- {type: capability, id: mark-dose-taken}
- {type: entity, id: settings, facts: [Action when dismissing notification]}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/NotificationIntentBuilder.kt#NotificationIntentBuilder
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/ReminderNotificationFactory.kt#ReminderNotificationFactory
---

# Dismissing a reminder notification performs the chosen action

Swiping a reminder notification away skips the dose, snoozes it or takes it, as Action when dismissing notification says (Skip dose by default); the notification then offers the other two actions as buttons.
