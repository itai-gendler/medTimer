---
appliesTo:
- {type: entity, id: reminder-event, effect: creates, to: Skipped}
permits:
- actors:
  - user
  when:
  - {fact: Cannot be skipped, is: 'Off'}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ScheduledReminderActions.kt#ScheduledReminderActions
---

# Only a dose that can be skipped is skipped ahead of time

A scheduled dose is skipped in advance only when its medicine is not marked Medicine cannot be skipped.
