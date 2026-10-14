---
entities:
- {entity: tag, shows: [Name], collects: [Name]}
- {entity: medicine, shows: [Name]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/tags/TagsFragment.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/tags/TagDataFromMedicine.kt#TagDataFromMedicine
---

# Tags

Every tag, with those of one medicine selected, where tags are added, selected, deselected and deleted.
