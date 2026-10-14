---
domain: overview
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/StockIntentBuilder.kt
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/NotificationProcessor.kt#NotificationProcessor
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ActionsVisitor.kt#ActionsVisitor
---

# Acknowledge notice

The User acknowledges an out-of-stock or expiration notice, by dismissing its notification or in the Overview.
