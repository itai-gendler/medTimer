---
domain: overview
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/ScheduleNextReminderNotificationProcessor.kt#ScheduleNextReminderNotificationProcessor
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/ReminderNotificationProcessor.kt#ReminderNotificationProcessor
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/ReminderScheduler.kt#ReminderScheduler
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/SchedulingFactory.kt#SchedulingFactory
- kind: doc
  role: intent
  target: docs/reminder_flow.md
---

# Raise reminder

The Product raises each enabled reminder when it is due: it records a raised event and notifies the User, as an alarm for High + Alarm, or takes the dose silently for a reminder that is taken automatically.
