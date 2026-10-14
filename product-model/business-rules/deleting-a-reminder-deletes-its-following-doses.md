---
appliesTo:
- {type: capability, id: delete-reminder}
- {type: entity, id: linked-reminder}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/LinkedReminderHandling.kt#LinkedReminderHandling
---

# Deleting a reminder deletes the reminders that follow it

Every linked reminder that follows a deleted reminder, directly or through other linked reminders, is deleted with it.
