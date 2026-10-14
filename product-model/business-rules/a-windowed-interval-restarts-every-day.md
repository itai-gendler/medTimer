---
appliesTo:
- {type: capability, id: raise-reminder}
- {type: entity, id: windowed-interval-reminder}
references:
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/WindowedIntervalScheduling.kt#WindowedIntervalScheduling
---

# A windowed interval restarts at the daily start time

A windowed interval reminder raises its first dose of the day at the daily start time and further doses every interval until the daily end time; a dose that would fall after the end moves to the next day's start.
