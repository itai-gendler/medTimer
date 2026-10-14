---
entities:
- {entity: tag, shows: [Name]}
- {entity: settings, shows: [Tag filter], collects: [Tag filter]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/tags/TagDataFromPreferences.kt#TagDataFromPreferences
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/TagFilterViewModel.kt#TagFilterViewModel
---

# Tag filter

Every tag, with those the lists are filtered by selected.
