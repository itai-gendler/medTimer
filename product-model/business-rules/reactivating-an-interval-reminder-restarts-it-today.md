---
appliesTo:
- {type: capability, id: activate-all-reminders}
- {type: entity, id: interval-reminder, facts: [Interval start time]}
references:
- kind: code
  role: implementation
  target: core/common/src/main/java/com/futsch1/medtimer/core/common/helpers/ReminderHelper.kt#setRemindersActive
---

# Activating all reminders restarts a continuous interval today

When Activate all reminders enables a continuous interval reminder that was disabled, its interval start time moves to today at the same time of day.
