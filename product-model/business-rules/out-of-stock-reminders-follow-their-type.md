---
appliesTo:
- {type: capability, id: remind-out-of-stock}
- {type: entity, id: out-of-stock-reminder}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/StockHandlingProcessor.kt#StockHandlingProcessor
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/OutOfStockScheduling.kt#OutOfStockScheduling
---

# An out-of-stock reminder notifies once, always or daily below its threshold

Once notifies when a taken dose brings the stock from above the threshold to or below it; Always notifies after every taken dose while the stock is at or below it; Daily notifies once a day at its time while the stock is at or below it.
