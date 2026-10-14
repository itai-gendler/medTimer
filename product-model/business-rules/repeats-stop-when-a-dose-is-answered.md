---
appliesTo:
- {type: capability, id: repeat-reminder}
- {type: capability, id: mark-dose-taken}
- {type: capability, id: skip-dose}
- {type: entity, id: reminder-event, facts: [Remaining repeats]}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/RepeatProcessor.kt#RepeatProcessor
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/NotificationProcessor.kt#NotificationProcessor
---

# Repeats stop once a dose is answered

A repeated reminder stops repeating when its dose is taken or skipped, or when no repetitions remain.
