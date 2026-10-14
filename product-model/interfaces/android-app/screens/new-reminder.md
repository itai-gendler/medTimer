---
entities:
- {entity: medicine, shows: [Name, Stock amount, Unit]}
- {entity: time-based-reminder, shows: [Dosage, Time], collects: [Dosage, Time]}
- {entity: interval-reminder, shows: [Dosage, Interval, Interval start time, Interval start condition], collects: [Dosage, Interval, Interval start time, Interval start condition]}
- {entity: windowed-interval-reminder, shows: [Dosage, Interval, Daily start time, Daily end time, Interval start condition], collects: [Dosage, Interval, Daily start time, Daily end time, Interval start condition]}
- {entity: out-of-stock-reminder, shows: [Reminder threshold, Out of stock reminder, Time], collects: [Reminder threshold, Out of stock reminder, Time]}
- {entity: expiration-reminder, shows: [Expiration reminder, Remind days before expiration, Time], collects: [Expiration reminder, Remind days before expiration, Time]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/dialogs/NewReminderTypeDialog.kt#NewReminderTypeDialog
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/dialogs/NewReminderDialog.kt#NewReminderDialog
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/dialogs/NewReminderStockDialog.kt#NewReminderStockDialog
---

# Add reminder

Creating a reminder for a medicine: choosing its type (time based, continuous interval, windowed interval, out of stock or expiration date) and then its dosage and timing.
