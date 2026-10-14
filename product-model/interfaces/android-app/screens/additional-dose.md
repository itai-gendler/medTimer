---
entities:
- {entity: medicine, shows: [Name]}
- {entity: time-based-reminder, shows: [Dosage]}
- {entity: linked-reminder, shows: [Dosage]}
- {entity: interval-reminder, shows: [Dosage]}
- {entity: windowed-interval-reminder, shows: [Dosage]}
- {entity: reminder-event, collects: [Medicine name, Dosage, Taken or skipped time]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/manualDose/ManualDoseDialog.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/manualDose/ManualDoseViewModel.kt#ManualDoseViewModel
---

# Log additional dose

Logging a dose no reminder asked for: choosing a medicine (or entering a custom one), its dosage and the time it was taken.
