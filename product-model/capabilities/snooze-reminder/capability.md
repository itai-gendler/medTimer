---
domain: overview
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/SnoozeProcessor.kt#SnoozeProcessor
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/CustomSnoozeHandler.kt#CustomSnoozeHandler
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/NotificationIntentBuilder.kt#NotificationIntentBuilder
---

# Snooze reminder

The User puts a reminder off for the snooze duration, or for a duration they enter each time, after which it notifies again.
