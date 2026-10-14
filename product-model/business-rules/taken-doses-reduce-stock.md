---
appliesTo:
- {type: capability, id: mark-dose-taken}
- {type: capability, id: log-additional-dose}
- {type: capability, id: raise-reminder}
- {type: entity, id: medicine}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/NotificationProcessor.kt#NotificationProcessor
- kind: code
  role: implementation
  target: core/common/src/main/java/com/futsch1/medtimer/core/common/helpers/MedicineHelper.kt#MedicineHelper
- kind: doc
  role: intent
  target: docs/UseCases.md
---

# A taken dose reduces its medicine's stock by its dosage

When a dose of a medicine that tracks stock is taken, whether answered, taken in advance, taken automatically or logged as an additional dose, the medicine's stock falls by the first number in the dose's dosage ("75 mg" or "Take 1 pill" both work). A dosage without a number changes no stock. The event keeps the stock before and after.
