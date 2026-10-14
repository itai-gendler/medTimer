---
entities:
- {entity: reminder-event, shows: [Medicine name, Dosage, Reminded time, Taken or skipped time, Tags]}
- {entity: medicine, shows: [Name, Color, Half-life, Time to peak]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/statistics/StatisticsScreen.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/statistics/StatisticsScreenViewModel.kt#StatisticsScreenViewModel
---

# Analysis

The dose history analysed four ways: charts of taken and skipped doses over a chosen range, a searchable table of every taken or skipped event, a month calendar, and estimated levels of medicines with a half-life and time to peak.
