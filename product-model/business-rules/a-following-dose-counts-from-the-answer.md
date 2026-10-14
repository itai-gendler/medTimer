---
appliesTo:
- {type: capability, id: add-linked-reminder}
- {type: capability, id: raise-reminder}
- {type: entity, id: linked-reminder}
references:
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/LinkedScheduling.kt#LinkedScheduling
- kind: doc
  role: intent
  target: docs/UseCases.md
---

# A following dose is reminded its delay after the previous dose is answered

A linked reminder notifies its delay after the dose it follows was taken or skipped, not after it was raised; the delay is under 24 hours and may reach into the next day.
