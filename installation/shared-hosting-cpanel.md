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

# 🤝 Shared Hosting / cPanel

This section will guide you **step by step** through the process of deploying **Evaluator** on a shared hosting service using **cPanel**.

### Step 1 - Upload the Files

1. **Download** the project folder `evaluator.zip` from **CodeCanyon**.
2. **Log in** to your **cPanel** account.
3. Go to your hosting’s **root directory**.
   * For most shared hosting services, this is usually the **public\_html** folder (The exact folder name may vary depending on your hosting provider).
4. **Upload** the `evaluator.zip` file to this folder.

{% hint style="success" %}
Direct uploading through cPanel can be time consuming and error-prone. We recommend using a free FTP client such as **FileZilla** for a faster and more reliable upload process.
{% endhint %}

5. **Unzip** the `evaluator.zip` file in your hosting directory.
6. **Create a `.env` file** in the same folder.
   * Make sure the file **has no extension** (it should be just `.env`).
7. **Copy the contents** of the `*.env.production.example` file into this new `.env` file.

### Step 2 - Setting up project details in `.env`

{% hint style="warning" %}
Before diving into the section below, we strongly recommend referring to the [.env](../miscellaneous/.env.md) section of this document.
{% endhint %}

1. **Open the `.env` file.**
2. In the top section, change project details as below.
3. If values contain spaces, make sure to wrap them inside **double quotes.**

```
APP_NAME=Laravel        -> Replace this with the name of your site
APP_ENV=production
APP_KEY=
APP_DEBUG=false
APP_URL=http://localhost  -> Change this to your project domain
```

**APP\_NAME**\
This must be the name of your site/company;

* Example: if your site name is _Smart Evaluator_, the value must be set as:

```
APP_NAME="Smart Evaluator"
```

**APP\_URL (!important)**\
This must be the domain of your site;

* Example: if your site domain is `https://evaluator.org`, the value must be set as:

```
APP_URL="https://evaluator.org"
```

***

### Step 3 - Create and setup MySQL Database

1. In your hosting control panel, go to **MySQL Databases**.
2. Create a new database (e.g. `evaluator_db`).
3. Create a new database user and password.

{% hint style="danger" %}
&#x20;Don't use **#** in database password string and make sure to use a strong password. Keep these details for later use.
{% endhint %}

4. Assign the user to the database with **All Privileges**.
   1. &#x20;In cPanel you can do this by navigating to the "Manage User Privileges" section, choose the privileges you want to assign to the user for the  specific database, then click on "Make Changes". Give user Full Privilege.

### **Step 4 - Add database details :**

Add manually database details via **.env** file, follow these steps:

* Locate the `.env` File: The `.env` file is located in the root directory of your Laravel project. Use a text editor to open the file.
* Find the Database Configuration Section: Look for the section in the `.env` file that contains the database configuration variables. It typically starts with `DB_`.
* Set Database Connection Details: Update the values of the following variables to match your database configuration:

```
Database Host = localhost 
Database Port = 3306 
Database Name = your_database_name 
Database User = your_database_user_name 
Database Password = your_database_password
```

* `DB_CONNECTION`: Specifies the database connection driver. For MySQL, use `mysql`.
* `DB_HOST`: Specifies the database server host name or IP address. (default is localhost or 127.0.0.1).
* `DB_PORT`: Specifies the port number on which the database server is running (default is 3306 for MySQL).
* `DB_DATABASE`: Specifies the name of the database you want to connect to.
* `DB_USERNAME`: Specifies the username for accessing the database.
* `DB_PASSWORD`: Specifies the password for the database user.
* Save the Changes: Save the `.env` file after updating the database configuration.

### Step 6 - Setup Email&#x20;

Please refer the dedicated [section](mail-setup.md).

### Step 7 - Setup Queue&#x20;

Please refer the dedicated [section](queue-setup.md).

### Step 8 - Theming

Please refer the dedicated [section](../theming.md).

{% hint style="danger" %}
You must follow all the above steps before continuing final step Setup Wizard
{% endhint %}

### Step 9 - Setup Wizard

1.  Open your browser and visit:

    ```
    https://yourdomain.com/public/setup
    ```

{% hint style="info" %}
You may notice the **public** suffix in the URL above. This appears because the site’s entry point is located in the project’s **public** folder.

\
Keeping this structure intact is crucial for security reasons. However, you can remove the suffix if needed. Please follow this [guide](../faq/installation.md) to do that.
{% endhint %}

1. The **Evaluator** setup wizard will appear.

<figure><img src="../.gitbook/assets/Screenshot from 2025-10-27 16-24-30.png" alt=""><figcaption></figcaption></figure>

1. Click **Start Setup**.
2. The setup wizard includes a few steps. Complete all steps to successfully set up the evaluator.
3. You will see a success message once the setup is complete.

{% hint style="info" %}
Refer [installation](broken-reference) issue for common issues.
{% endhint %}

<figure><img src="../.gitbook/assets/Screenshot from 2025-10-27 16-29-44.png" alt=""><figcaption></figcaption></figure>

Congratulations! You’re all set to use the evaluator. 🥳
