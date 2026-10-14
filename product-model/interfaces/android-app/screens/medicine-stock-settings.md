---
entities:
- {entity: medicine, shows: [Stock amount, Unit, Refill size, Production date, Expiration date, Estimated run out date], collects: [Stock amount, Unit, Refill size, Production date, Expiration date]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/medicineSettings/StockSettingsFragment.kt#StockSettingsFragment
- kind: code
  role: implementation
  target: feature/ui/src/main/res/xml/stock_settings.xml
---

# Medicine stock settings

A medicine's stock: the amount left and its unit, the estimated run-out date, the refill size with Refill now, the production and expiration dates, and buttons to create out-of-stock and expiration reminders.
