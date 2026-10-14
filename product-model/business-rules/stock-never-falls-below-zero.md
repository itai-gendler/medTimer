---
appliesTo:
- {type: entity, id: medicine, facts: [Stock amount]}
- {type: capability, id: mark-dose-taken}
- {type: capability, id: log-additional-dose}
references:
- kind: code
  role: implementation
  target: core/database/src/main/java/com/futsch1/medtimer/database/dao/MedicineDao.kt
---

# Stock never falls below zero

A medicine's stock stops at zero however much is taken.
