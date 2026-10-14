---
appliesTo:
- {type: entity, id: reminder-event, effect: changes, facts: [Medicine name, Dosage, Notes, Reminded time]}
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/EditEventViewModel.kt#EditEventViewModel
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/VariableAmountHandler.kt#VariableAmountHandler
---

# Only the User changes an event's name, dosage, notes or reminded time

An event's medicine name, dosage, notes and reminded time change only when the User enters a dosage on taking it, reschedules it or corrects it; the Product keeps them as raised.
