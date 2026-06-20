# WordPress Installation and Configuration

## Objective

The objective of this phase was to deploy and configure WordPress on the Ubuntu Server using the LEMP (Linux, Nginx, MariaDB, PHP) stack.

WordPress was installed manually to provide a better understanding of Linux server administration and web application deployment.

---

## Environment

| Component        | Details       |
| ---------------- | ------------- |
| Operating System | Ubuntu Server |
| Web Server       | Nginx         |
| Database Server  | MariaDB       |
| PHP Version      | PHP 8.5       |
| Application      | WordPress     |

---

## What is WordPress?

WordPress is an open-source content management system (CMS) used to create websites and blogs.

WordPress uses:

* PHP
* MariaDB
* Nginx
* Linux

Together, these components form a LEMP stack.

---

## Downloading WordPress

The latest version of WordPress was downloaded from the official website.

```bash
cd /tmp

curl -LO https://wordpress.org/latest.tar.gz
```

---

## Extracting WordPress

The archive was extracted.

```bash
tar -xzf latest.tar.gz
```

---

## Deploying WordPress Files

The extracted files were copied to the web server directory.

```bash
sudo cp -R /tmp/wordpress /var/www/
```

---

## Setting File Ownership

The web server requires appropriate file ownership.

```bash
sudo chown -R www-data:www-data /var/www/wordpress
```

---

## Setting File Permissions

Directory and file permissions were configured.

Directories:

```bash
sudo find /var/www/wordpress/ -type d -exec chmod 755 {} \;
```

Files:

```bash
sudo find /var/www/wordpress/ -type f -exec chmod 644 {} \;
```

These permissions help improve server security.

---

## Creating the WordPress Configuration File

The sample configuration file was copied.

```bash
cd /var/www/wordpress

cp wp-config-sample.php wp-config.php
```

---

## Configuring Database Settings

The WordPress configuration file was edited.

```bash
nano wp-config.php
```

The following values were configured:

Database name:

```text
wordpress
```

Database user:

```text
wordpress
```

Database password:

```text
********
```

Database host:

```text
localhost
```

---

## Configuring Authentication Keys

Unique authentication keys and salts were generated and added to the configuration file.

These keys improve the security of user sessions and cookies.

---

## Verifying WordPress Files

The WordPress directory contents were verified.

```bash
ls -la /var/www/wordpress
```

The output confirmed the presence of:

* wp-config.php
* wp-admin
* wp-content
* wp-includes

---

## Preparing for Web Server Integration

At this stage:

* WordPress files were deployed.
* Database configuration was completed.
* File ownership and permissions were configured.
* Authentication keys were added.

The application was ready for Nginx virtual host configuration.

---

## Commands Used

```bash
cd /tmp

curl -LO https://wordpress.org/latest.tar.gz

tar -xzf latest.tar.gz

sudo cp -R /tmp/wordpress /var/www/

sudo chown -R www-data:www-data /var/www/wordpress

sudo find /var/www/wordpress/ -type d -exec chmod 755 {} \;

sudo find /var/www/wordpress/ -type f -exec chmod 644 {} \;

cd /var/www/wordpress

cp wp-config-sample.php wp-config.php

nano wp-config.php

ls -la /var/www/wordpress
```

---

## Skills Demonstrated

* Linux file management
* Application deployment
* File ownership management
* Linux permissions
* WordPress configuration
* Database integration
* Basic web application security

---

## Result

At the end of this phase:

* WordPress was successfully downloaded.
* Application files were deployed.
* File ownership and permissions were configured.
* Database settings were completed.
* Authentication keys were configured.
* WordPress was prepared for Nginx integration.

---

## Screenshots

Suggested screenshots:

* WordPress download
* WordPress extraction
* Copying files
* File ownership configuration
* Directory permissions
* wp-config.php configuration
* WordPress directory listing
