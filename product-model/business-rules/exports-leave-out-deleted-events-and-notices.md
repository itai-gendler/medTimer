---
appliesTo:
- {type: capability, id: export-event-data}
- {type: entity, id: reminder-event}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/AppOptionsViewModel.kt#AppOptionsViewModel
- kind: code
  role: implementation
  target: core/database/src/main/java/com/futsch1/medtimer/database/ReminderEventRepositoryImpl.kt#ReminderEventRepositoryImpl
---

# Event exports leave out deleted events and acknowledged notices

An event export holds the raised, taken and skipped events and additional doses, narrowed by the tag filter, and none that were deleted or acknowledged.
