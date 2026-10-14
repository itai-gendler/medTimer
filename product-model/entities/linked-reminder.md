---
domain: medicine
relations:
- entity: reminder-event
  verb: raises
  cardinality: one-to-many
- entity: linked-reminder
  verb: is followed by
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
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/LinkedScheduling.kt#LinkedScheduling
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/LinkedReminderHandling.kt#LinkedReminderHandling
---

# Linked reminder

A reminder for a following dose: it notifies a set delay after the dose it follows was taken or skipped.
The product also calls it a reminder for the following dose.

## Information kept

- **Dosage** — the amount to take as the person writes it, such as "1 pill" or "75 mg"; its first number is what stock tracking deducts
- **Enabled** — whether the reminder notifies at all; a disabled reminder keeps its configuration
- **Active from** — the first date the reminder may notify, if limited
- **Active until** — the last date the reminder may notify, if limited
- **Instructions** — dosing instructions shown with the reminder, such as "before the meal"
- **Enter dosage when taken** — whether the person is asked for the dosage actually taken when they mark the dose taken
- **Automatically mark as taken** — whether the dose is recorded as taken at its time without a notification, for example to only track stock
- **Notification priority** — Same as medicine, Default, High or High + Alarm
- **Delay** — how long after the previous dose was taken or skipped it notifies, under 24 hours
