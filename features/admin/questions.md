---
layout:
  width: default
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# ❓ Questions

### Features

* CRUD[^1] Questions
* Manage images
* Manage answers

### Attributes

* Difficulty
  * Easy
  * Medium
  * Hard
* Categories - Multiple allowed
* Answer type
  * Single - Question can only have one correct answer
  * Multiple - Can have multiple correct answers or single
* No of answers
* Content - WYSIWYG editor is provided

#### Optional Attributes

* Images - Advanced image editor is provided

### Status

A question can has following status based on its completeness.

* Completed
* Incompleted

### Completeness

A question is considered completed when following requirements meets.

* Must assign answers that match the no of answers
* At least one correct answer must present



[^1]: Create, Read (search, filter), Update, Delete
