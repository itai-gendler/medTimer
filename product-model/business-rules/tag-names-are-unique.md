---
appliesTo:
- {type: capability, id: add-tag}
- {type: entity, id: tag}
references:
- kind: code
  role: implementation
  target: core/database/src/main/java/com/futsch1/medtimer/database/TagRepositoryImpl.kt#TagRepositoryImpl
---

# No two tags share a name

Adding a tag with the name of an existing one gives the existing tag instead of creating another.
