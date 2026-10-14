---
domain: overview
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/StockHandlingProcessor.kt#StockHandlingProcessor
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/OutOfStockScheduling.kt#OutOfStockScheduling
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/OutOfStockNotificationFactory.kt#OutOfStockNotificationFactory
---

# Remind out of stock

The Product notifies that a medicine's stock is at or below an out-of-stock reminder's threshold: once when it falls to it, after every taken dose below it, or daily while below it.
