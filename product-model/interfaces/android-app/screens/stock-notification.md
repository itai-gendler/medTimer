---
entities:
- {entity: reminder-event, shows: [Medicine name, Dosage, Type]}
- {entity: medicine, shows: [Name, Stock amount, Refill size, Expiration date]}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/OutOfStockNotificationFactory.kt#OutOfStockNotificationFactory
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/ExpirationDateNotificationFactory.kt#ExpirationDateNotificationFactory
---

# Stock notification

The notification that a medicine is running out of stock, with Refill, or that it expires, dismissed to acknowledge it.
