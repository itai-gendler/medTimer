---
entities:
- {entity: medicine, shows: [Color, Notification priority, Cannot be skipped, Half-life, Time to peak], collects: [Color, Notification priority, Cannot be skipped, Half-life, Time to peak]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/medicineSettings/MedicineSettingsFragment.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/medicineSettings/MedicineDataStore.kt#MedicineDataStore
- kind: code
  role: implementation
  target: feature/ui/src/main/res/xml/medicine_settings.xml
---

# Medicine settings

A medicine's color, notification priority, whether its doses can be skipped, and the half-life and time to peak its level estimate uses.
