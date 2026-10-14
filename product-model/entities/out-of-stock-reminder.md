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
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/StockHandlingProcessor.kt#StockHandlingProcessor
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/OutOfStockScheduling.kt#OutOfStockScheduling
---

# Out of stock reminder

A reminder that the medicine's stock has reached a threshold.

## Information kept

- **Enabled** — whether it notifies at all
- **Reminder threshold** — the stock at or below which it notifies
- **Out of stock reminder** — Once when falling below threshold, Always when below threshold (after every taken dose) or Daily when below threshold
- **Time** — the time of day a daily reminder notifies
