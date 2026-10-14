---
entities:
- {entity: reminder-event, shows: [Dosage, Medicine name], collects: [Dosage]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/VariableAmountHandler.kt#VariableAmountHandler
---

# Dosage entry

The prompt for the dosage actually taken, shown when a dose that asks for its dosage is marked taken.
