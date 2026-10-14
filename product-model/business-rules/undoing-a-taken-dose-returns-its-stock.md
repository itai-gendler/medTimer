---
appliesTo:
- {type: capability, id: skip-dose}
- {type: capability, id: delete-reminder-event}
- {type: capability, id: re-raise-event}
- {type: capability, id: edit-reminder-event}
- {type: entity, id: medicine}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/NotificationProcessor.kt#NotificationProcessor
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ActionsVisitor.kt#ActionsVisitor
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/EditEventViewModel.kt#EditEventViewModel
---

# Undoing a taken dose gives its stock back

For a dose raised by a reminder, changing it from taken to skipped, deleting it or re-raising it adds its dosage back to the medicine's stock, and editing its dosage or state corrects the stock by the difference.
