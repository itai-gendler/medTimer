---
domain: medicine
relations:
- entity: reminder-event
  verb: raises
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: core/domain/src/main/java/com/futsch1/medtimer/core/domain/model/Reminder.kt#Reminder
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/advancedReminderPreferences/ReminderDataStore.kt#ReminderDataStore
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/ExpirationDateScheduling.kt#ExpirationDateScheduling
---

# Expiration reminder

A reminder that the medicine's expiration date has come or is near.

## Information kept

- **Enabled** — whether it notifies at all
- **Expiration reminder** — Once or Daily
- **Remind days before expiration** — how many days before the expiration date it starts reminding
- **Time** — the time of day it notifies
