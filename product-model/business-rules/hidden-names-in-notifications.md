---
appliesTo:
- {type: capability, id: raise-reminder}
- {type: capability, id: remind-out-of-stock}
- {type: capability, id: remind-expiration-date}
- {type: entity, id: settings, facts: [Hide medication name in notification]}
references:
- kind: code
  role: implementation
  target: core/common/src/main/java/com/futsch1/medtimer/core/common/helpers/MedicineHelper.kt#MedicineHelper
---

# Notifications hide medicine names when asked

While Hide medication name in notification is on, reminder, stock and expiration notifications show only the first letter of each medicine name.
