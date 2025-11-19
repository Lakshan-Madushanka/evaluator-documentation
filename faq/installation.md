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

# ⚙️ Installation&#x20;

### Remove Public From URL <a href="#remove-public-from-url" id="remove-public-from-url"></a>

{% hint style="info" %}
Set your web server’s root directory to the **public** folder of the evaluator, if possible. If you do not have permission to do so, follow the guide below.
{% endhint %}

To remove the public from the URL create a **.htaccess** file in the root folder and write following code.

```
<IfModule mod_rewrite.c>
	RewriteEngine On 
	RewriteRule ^(.*)$ public/$1 [L]
</IfModule>
```

To remove the public from URL and Force HTTPS redirection create a .htaccess file in the root folder and write the following code.

```
<IfModule mod_rewrite.c>
	RewriteEngine On
	RewriteCond %{HTTPS} !=on
	RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301,NE] 
	RewriteRule ^(.*)$ public/$1 [L]
</IfModule>
```

### Remove Public From URL for LightSpeed Server (vercel, netlify, etc.)

To remove the public from the URL in LightSpeed Server; create a .htaccess file in the root folder and write following code.

```
RewriteEngine On 
RewriteRule ^(.*)$ public/$1 [L]
```

To remove the public from URL and Force HTTPS redirection in LightSpeed Server -> create a .htaccess file in the root folder and write the following code.

```
RewriteEngine On
RewriteCond %{HTTPS} !=on
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301,NE] 
RewriteRule ^(.*)$ public/$1 [L]
```

### Support Older MySQL Versions

If your server is running MySQL below version 5.7.7 or MariaDB older than 10.2.2, you should enable support for older database versions. You can do this by setting the `SUPPORT_OLDER_DB_VERSIONS` key in your `.env` file.

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=evaluator
DB_USERNAME=root
DB_PASSWORD=
SUPPORT_OLDER_DB_VERSIONS=true -> set this to true
```

### Unable to Create Storage Link

The storage link is essential for mapping uploaded images to the public directory. However, your hosting service may not allow you to create a symbolic link. We provide a solution for this as well  simply set the `SUPPORT_SYMLINK` key to `false` in your `.env` file.

```
BROADCAST_DRIVER=log
CACHE_DRIVER=file
FILESYSTEM_DISK=local
SUPPORT_SYMBLINK=false -> set this to false
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
SESSION_LIFETIME=120
```
