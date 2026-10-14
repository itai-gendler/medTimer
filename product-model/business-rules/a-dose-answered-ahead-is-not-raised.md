---
appliesTo:
- {type: capability, id: mark-dose-taken}
- {type: capability, id: skip-dose}
- {type: capability, id: reschedule-reminder}
- {type: capability, id: raise-reminder}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ReminderEventCreator.kt#ReminderEventCreator
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/OverviewViewModel.kt#OverviewViewModel
---

# A dose answered ahead of time is not raised at its time

Taking, skipping or rescheduling a scheduled dose before it is due records it for its reminder and time, so its reminder does not notify again for that time.
