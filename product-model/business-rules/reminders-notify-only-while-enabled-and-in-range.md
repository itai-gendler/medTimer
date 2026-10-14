---
appliesTo:
- {type: capability, id: raise-reminder}
- {type: entity, id: time-based-reminder}
- {type: entity, id: linked-reminder}
- {type: entity, id: interval-reminder}
- {type: entity, id: windowed-interval-reminder}
references:
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/ReminderScheduler.kt#ReminderScheduler
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/StandardScheduling.kt#StandardScheduling
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/IntervalScheduling.kt#IntervalScheduling
---

# A reminder notifies only while enabled and within its active dates

A disabled reminder never notifies, and an enabled one only between its Active from and Active until dates when they are set.
