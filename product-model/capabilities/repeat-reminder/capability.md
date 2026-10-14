---
domain: overview
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/RepeatProcessor.kt#RepeatProcessor
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/ReminderNotificationProcessor.kt#ReminderNotificationProcessor
---

# Repeat reminder

While repeat reminders are on, the Product notifies an unanswered dose again after the time between repetitions, as often as the number of repetitions allows.
