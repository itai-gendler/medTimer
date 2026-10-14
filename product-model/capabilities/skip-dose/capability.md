---
domain: overview
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/NotificationProcessor.kt#NotificationProcessor
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/NotificationIntentBuilder.kt#NotificationIntentBuilder
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ReminderEventActions.kt#ReminderEventActions
---

# Skip dose

The User records that a dose was not taken, from its notification, its alarm or the Overview; a dose that was already taken gives its stock back.
