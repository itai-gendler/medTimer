---
appliesTo:
- {type: capability, id: raise-reminder}
- {type: entity, id: time-based-reminder}
references:
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/StandardScheduling.kt#StandardScheduling
- kind: doc
  role: context
  target: docs/UseCases.md
---

# A cyclic reminder notifies only on the active days of its cycle

Counting from the first cycle start, a cyclic reminder notifies on the first Active days of every cycle of Active days plus Pause days; weekday, day-of-month and active-date limits apply on top.
