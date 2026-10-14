---
domain: medicine
availability:
- {place: android-app}
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

The User adds a reminder to a medicine, choosing its type: time based, continuous interval, windowed interval, out of stock or expiration date. The stock settings offer the last two directly.
