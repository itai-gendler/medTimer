---
entities:
- {entity: reminder-event, shows: [Medicine name, Dosage, Notes, Reminded time, Taken or skipped time, Type, Cannot be skipped], collects: [Medicine name, Dosage, Notes, Reminded time, Taken or skipped time]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/EditEventSheetDialogFragment.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/EditEventViewModel.kt#EditEventViewModel
---

# Edit event

One event of the history: its medicine name, dosage, notes, reminded and taken times, and whether it was taken or skipped.
