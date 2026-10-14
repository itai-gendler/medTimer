---
appliesTo:
- {type: capability, id: raise-reminder}
- {type: entity, id: interval-reminder}
- {type: entity, id: windowed-interval-reminder}
references:
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/IntervalScheduling.kt#IntervalScheduling
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/WindowedIntervalScheduling.kt#WindowedIntervalScheduling
---

# An interval counts from the reminder or from the answer, as chosen

The next dose of an interval reminder is due one interval after the previous one was raised, or after it was taken or skipped when the interval starts when taken or skipped; while the previous dose is unanswered under that condition, no next dose is due.
