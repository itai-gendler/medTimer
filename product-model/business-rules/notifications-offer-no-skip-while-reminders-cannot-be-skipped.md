---
appliesTo:
- {type: capability, id: skip-dose}
- {type: capability, id: snooze-reminder}
- {type: entity, id: settings, facts: [Reminders cannot be skipped]}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/NotificationIntentBuilder.kt#NotificationIntentBuilder
---

# Notifications offer no skip while reminders cannot be skipped

While Reminders cannot be skipped is on, reminder notifications and alarms show no Skipped, and dismissing a notification whose action is Skip dose snoozes it instead.
