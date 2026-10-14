---
appliesTo:
- {type: capability, id: delete-reminder-event}
- {type: capability, id: re-raise-event}
- {type: entity, id: reminder-event}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ActionsVisitor.kt#ActionsVisitor
- kind: code
  role: implementation
  target: core/database/src/main/java/com/futsch1/medtimer/database/ReminderEventRepositoryImpl.kt#ReminderEventRepositoryImpl
---

# A deleted event is not raised again; a re-raised one is

Deleting an event hides it from the history but its reminder still counts as answered for that time; Re-raise event removes it so that its reminder notifies again.
