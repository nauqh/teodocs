---
hide:
  - navigation
---
# Changelog

!!! note
    Major and minor releases also include the changes specified in prior development releases.

## Updates (2024-02-10)

To be released

---

## Refactor (2024-01-03)

### Features
=== "Question forum"

    ![Music](../assets/exam.png)

    - Alert moderator regarding recent forum query
    - Add embed link to forum thread through discord embed
    - Obtain and communicate resolution to address query posted

=== "Exam request"

    ![Music](../assets/dm.png)
   
    - Notify and embed link to exam platform

### Bugfixes
- [x] Resolved issue where bot catches all `NewMessageCreate` events.
- [x] Resolved bug where bot send notification twice on new thread created.
