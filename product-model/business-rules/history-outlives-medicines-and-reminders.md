---
appliesTo:
- {type: capability, id: delete-medicine}
- {type: capability, id: edit-medicine}
- {type: capability, id: delete-reminder}
- {type: entity, id: reminder-event}
references:
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/ReminderEventFactory.kt#buildReminderEvent
- kind: code
  role: context
  target: core/ui/src/main/res/values/strings.xml
  title: intro_analysis_description
---

# The history outlives changes to medicines and reminders

An event keeps the medicine name, dosage and tags it was raised with: renaming or deleting the medicine, changing or deleting the reminder, or retagging leaves the history as it was.
