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

# 📋 Requirements

| Requirement | Version                                                                                                                          |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------- |
| PHP         |  >= 8.3 (8.3 or higher)                                                                                                          |
| Server      | Nginx                                                                                                                            |
| Database    | MySQL 5.7.7+ or MariaDB 10.2.2+ recommended refer [here](../faq/installation.md#support-older-mysql-versions) for older versions |

### PHP Extensions

* BCMath PHP Extension
* Ctype PHP Extension
* cURL PHP Extension
* DOM PHP Extension
* Fileinfo PHP Extension
* Filter PHP Extension
* Hash PHP Extension
* Mbstring PHP Extension
* OpenSSL PHP Extension
* PDO PHP Extension
* Session PHP Extension
* Tokenizer PHP Extension
* XML PHP Extension

### **File & Folder Permissions**

Laravel needs certain folder permissions to run properly. Make sure the following folder has the correct access rights & all permissions must be recursive(must applicable to all subfolders):

* **/bootstrap**→ Set permission to **775**
* **/storage** → Set permission to **775**&#x20;
* **/public** → Set permission to **775**

For Linux or macOS, you can run:

```
chmod -R 775 storage bootstrap public
chown -R www-data:www-data storage bootstrap/cache public
```

For Windows, make sure these directories allow **write access** via file explorer or CMD.
