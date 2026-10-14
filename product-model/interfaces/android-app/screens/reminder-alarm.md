---
entities:
- {entity: reminder-event, shows: [Medicine name, Dosage, Reminded time]}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/alarm/ReminderAlarmActivity.kt
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/alarm/AlarmFragment.kt
---

# Alarm

The full-screen alarm shown for a dose whose priority is High + Alarm, with Taken, Skipped and Snooze.
