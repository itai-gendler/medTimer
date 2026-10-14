---
domain: medicine
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/MedicinesScreen.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/EditMedicineActions.kt#EditMedicineActions
- kind: code
  role: implementation
  target: core/database/src/main/java/com/futsch1/medtimer/database/MedicineRepositoryImpl.kt#MedicineRepositoryImpl
---

# Delete medicine

The User deletes a medicine with its reminders; the events it raised stay in the history.
