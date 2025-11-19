---
coverY: 0
layout:
  width: default
  cover:
    visible: false
    size: full
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

# 📧 Mail Setup

The evaluator can work without an email setup, but we highly recommend enabling it.

### Why Do I Need to Configure Email?

Evaluators use a unique code for candidates to access the questionnaire. Email is the most effective method for delivering this code to the relevant candidates, allowing them to start the quiz conveniently. Otherwise, site administrators would need to find alternative ways to share the code, such as communicating it manually.

### Prerequisites

* Email account

### **Configure Mail Account**

Setting up an email account is very easy. All you need to do is configure the correct mail settings in the [**.env**](../miscellaneous/.env.md) file.

Open the **.env** file, locate the mail configuration section, and fill in the values as shown below.

```
MAIL_DRIVER="Your mail driver"           → (e.g., smtp)
MAIL_HOST="Your mail host"               → (e.g., smtp.gmail.com)
MAIL_PORT="Your mail port"               → (e.g., 587)
MAIL_USERNAME="Your email ID"            → (e.g., yourname@gmail.com)
MAIL_PASSWORD="Your email password"      → (e.g., your email account password)
MAIL_ENCRYPTION="Your encryption type"   → (e.g., tls or ssl)
```

* **MAIL\_DRIVER:** Usually set as **smtp**
* **MAIL\_HOST:** For Gmail it is **smtp.gmail.com**, for others it could be **smtp.sendgrid.net**, etc.
* **MAIL\_PORT:** Common values are **587**, **465**, or **2525**, depending on your email provider
* **MAIL\_USERNAME:** The email ID used to send emails from your app
* **MAIL\_PASSWORD:** The actual password or app-specific password of your email
* **MAIL\_ENCRYPTION:** Usually **tls** or **ssl** (used to secure the connection)

If the email address is evaluator@gmail.com; values must be filled as following

```
MAIL_DRIVER=smtp
MAIL_HOST=smtp.gmail.com
MAIL_PORT=587
MAIL_USERNAME=evaluator@gmail.com
MAIL_PASSWORD=yourpassword
MAIL_ENCRYPTION=tls
```
