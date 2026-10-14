---
domain: overview
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/NotificationProcessor.kt#NotificationProcessor
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/ReminderProcessorBroadcastReceiver.kt#ReminderProcessorBroadcastReceiver
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ActionsVisitor.kt#ActionsVisitor
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/VariableAmountHandler.kt#VariableAmountHandler
---

# Mark dose taken

The User records that a dose was taken, from its notification, its alarm or the Overview, also ahead of time for a scheduled dose. A taken dose reduces the medicine's stock by its dosage.
