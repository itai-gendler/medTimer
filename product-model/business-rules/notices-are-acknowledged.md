---
appliesTo:
- {type: entity, id: reminder-event, effect: changes, to: Acknowledged}
permits:
- actors:
  - user
  when:
  - {fact: Type, is: Out of stock}
- actors:
  - user
  when:
  - {fact: Type, is: Expiration}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/NotificationProcessor.kt#NotificationProcessor
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ReminderEventActions.kt#ReminderEventActions
---

# Out-of-stock and expiration notices are only acknowledged

An out-of-stock or expiration notice is answered by acknowledging it, never by taking or skipping it; the User acknowledges it, also by refilling, and a refill is recorded as acknowledged.
