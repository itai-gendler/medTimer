---
appliesTo:
- {type: entity, id: reminder-event, effect: changes, to: Skipped}
permits:
- actors:
  - user
  when:
  - {fact: Cannot be skipped, is: 'Off'}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ReminderEventActions.kt#ReminderEventActions
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/NotificationIntentBuilder.kt#NotificationIntentBuilder
---

# Only a dose that can be skipped is skipped

The User skips a dose, or changes a taken one to skipped, only when its medicine is not marked Medicine cannot be skipped; such a dose can only be answered by taking it.
