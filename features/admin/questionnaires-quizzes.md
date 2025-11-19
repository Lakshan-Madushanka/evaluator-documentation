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

# 📝 Questionnaires/Quizzes

### Features

* CRUD[^1] Questionnaires
* Manage Questions
* Display Mode
* Print Mode

### Attributes

* Name
* Difficulty&#x20;
  * Easy
  * &#x20;Medium
  * &#x20;Hard
* Categories (multiple allowed)
* Answer type
  * Single - Allows questions with only one correct answer
  * Multiple - Allows questions with multiple correct answers, also allows s**ingle** types
* No of easy questions&#x20;
* No of medium questions
* No of hard questions
* No of total questions
* Allocated time

### Status

A questionnaire can be **complete** or **incomplete** until it meets the required constrains. Only completed questionnaires can be attached to a team or user.

### Completeness

A questionnaire is considered complete when following formula is satisfied.

**No of easy questions + No of medium questions + No of hard questions = No of total questions**

### Questions

Questions must meet following requirements to be able to attach to a questionnaire.

* Must be a completed question
* Must be corresponded to the difficulty level of the questionnaire
  * Easy - Only easy type questions can be attached.
  * Medium - Easy + Medium type questions can be attached.
  * Hard - Can attach any type of questions
* Must be corresponded to the category of the questionnaire - If questionnaire category is GN then all the questions must come from GN question type.
* Must be corresponded to the answer type
  * Single answer type - Only single answer type questions are allowed
  * Multiple answer type - Both answer type questions are allowed&#x20;
* No of {difficulty} questions count must be equal to the allowed {difficulty} level questions of the questionnaire - If allowed easy questions count is 5; then total easy questions count must be 5.

[^1]: Create, Read (search, filter), Update, Delete
