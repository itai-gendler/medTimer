---
appliesTo:
- {type: entity, id: reminder-event, effect: changes, to: Deleted}
permits:
- actors:
  - user
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ActionsVisitor.kt#ActionsVisitor
---

# Only the User deletes an event from the history

An answered event or notice is deleted from the history only when the User deletes it; the Product never deletes events on its own.
