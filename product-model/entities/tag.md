---
domain: medicine
references:
- kind: code
  role: implementation
  target: core/domain/src/main/java/com/futsch1/medtimer/core/domain/model/Tag.kt#Tag
- kind: code
  role: implementation
  target: core/database/src/main/java/com/futsch1/medtimer/database/TagRepositoryImpl.kt#TagRepositoryImpl
---

# Tag

A label given to medicines, for example the name of the person who takes them, shown in notifications,
the Overview and the medicine list and used to filter them.

## Information kept

- **Name** — the label; no two tags share a name
