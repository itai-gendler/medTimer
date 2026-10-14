---
appliesTo:
- {type: entity, id: reminder-event, effect: removes}
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/AppOptionsViewModel.kt#AppOptionsViewModel
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ActionsVisitor.kt#ActionsVisitor
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/database/backup/JSONReminderEventBackup.kt
---

# Events leave the history only when the User removes them

Events are removed only by the User: by re-raising one, clearing all history or restoring a backup with event data. Nothing expires from the history on its own.
