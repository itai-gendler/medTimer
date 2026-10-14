---
entities:
- {entity: medicine, shows: [Name, Icon, Notes], collects: [Name, Icon, Notes]}
- {entity: time-based-reminder, shows: [Dosage, Time, Enabled], collects: [Dosage, Time]}
- {entity: linked-reminder, shows: [Dosage, Delay, Enabled], collects: [Dosage, Delay]}
- {entity: interval-reminder, shows: [Dosage, Interval, Enabled], collects: [Dosage]}
- {entity: windowed-interval-reminder, shows: [Dosage, Interval, Enabled], collects: [Dosage]}
- {entity: out-of-stock-reminder, shows: [Reminder threshold, Time, Enabled], collects: [Time]}
- {entity: expiration-reminder, shows: [Remind days before expiration, Time, Enabled], collects: [Time]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/EditMedicineFragment.kt#EditMedicineFragment
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/EditMedicineActions.kt#EditMedicineActions
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/ReminderViewHolder.kt#ReminderViewHolder
---

# Medicine details

One medicine: its name, icon and notes, and its reminders, each with its dosage and time or delay and a summary of its advanced settings. From here the person adds reminders and opens the medicine's settings, stock, tags and calendar.
