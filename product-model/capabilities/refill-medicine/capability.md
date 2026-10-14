---
domain: medicine
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/RefillProcessor.kt#RefillProcessor
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/medicineSettings/StockSettingsFragment.kt#StockSettingsFragment
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/StockIntentBuilder.kt
---

# Refill medicine

The User records a refill, which adds the refill size to the medicine's stock and appears in the history as a stock refill.
