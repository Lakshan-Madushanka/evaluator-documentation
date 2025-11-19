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

# 🔐 Roles & Permissions

Evaluator has following roles.

* Super Admin - Setup will create a one for you.
* Admin - Can create from admin panel
* Candidate - No need to create; non login users

| Role        | Permissions                                                                                                    |
| ----------- | -------------------------------------------------------------------------------------------------------------- |
| Super Admin | All                                                                                                            |
| Admin       | <p>All except followings;</p><p><em>create, update, delete</em> Users<br>delete Teams<br>delete Categories</p> |
| Candidate   | Attempt Quiz                                                                                                   |
