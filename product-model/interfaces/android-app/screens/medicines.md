---
entities:
- {entity: medicine, shows: [Name, Icon, Color, Stock amount, Unit, Estimated run out date, Expiration date, Position]}
- {entity: tag, shows: [Name]}
- {entity: time-based-reminder, shows: [Time, Enabled]}
- {entity: linked-reminder, shows: [Enabled]}
- {entity: interval-reminder, shows: [Enabled]}
- {entity: windowed-interval-reminder, shows: [Enabled]}
- {entity: out-of-stock-reminder, shows: [Enabled]}
- {entity: expiration-reminder, shows: [Enabled]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/MedicinesFragment.kt#MedicinesFragment
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/MedicinesScreen.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/MedicinesScreenViewModel.kt#MedicinesScreenViewModel
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/MedicinesMenu.kt#MedicinesMenu
---

# Medicine

The list of medicines in their chosen order, each with its reminder times, remaining stock and estimated run-out date, warnings for low stock and expiry, its tags and whether all its reminders are inactive.
