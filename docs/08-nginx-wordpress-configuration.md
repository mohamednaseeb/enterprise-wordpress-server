# Nginx and WordPress Configuration

## Objective

The objective of this phase was to configure Nginx to serve the WordPress application and integrate it with PHP-FPM for dynamic content processing.

This configuration completed the web application stack and prepared the server for the WordPress installation wizard.

---

## Environment

| Component        | Details       |
| ---------------- | ------------- |
| Operating System | Ubuntu Server |
| Web Server       | Nginx         |
| PHP Processor    | PHP-FPM       |
| Database         | MariaDB       |
| Application      | WordPress     |

---

## Nginx Virtual Host

A dedicated Nginx server block was created for the WordPress website.

Configuration file:

```text
/etc/nginx/sites-available/wordpress
```

The configuration defined:

* Server listening on port 80
* Document root
* Index files
* PHP processing
* Security rules

---

## Configuring the Document Root

The document root was configured as:

```text
/var/www/wordpress
```

This directory contains the WordPress application files.

---

## Configuring PHP-FPM

Nginx was configured to forward PHP requests to PHP-FPM using a Unix socket.

Example:

```text
fastcgi_pass unix:/run/php/php8.5-fpm.sock;
```

This allows PHP scripts to be processed efficiently.

---

## Configuring Index Files

The server block was configured to load:

```text
index.php
index.html
index.htm
```

This ensures WordPress loads correctly.

---

## Protecting Sensitive Files

Access to hidden files was restricted.

Example:

```text
location ~ /\.ht {
    deny all;
}
```

This prevents access to sensitive configuration files.

---

## Enabling the Site

The Nginx site configuration was enabled.

```bash
sudo ln -s /etc/nginx/sites-available/wordpress \
/etc/nginx/sites-enabled/
```

---

## Removing the Default Site

The default Nginx configuration was removed.

```bash
sudo rm /etc/nginx/sites-enabled/default
```

This prevents conflicts between multiple server blocks.

---

## Testing the Configuration

The Nginx configuration was verified.

```bash
sudo nginx -t
```

Expected output:

```text
syntax is ok
test is successful
```

---

## Restarting Nginx

After successful validation, Nginx was restarted.

```bash
sudo systemctl restart nginx
```

Service status was verified.

```bash
sudo systemctl status nginx
```

---

## Verifying PHP-FPM

PHP-FPM was confirmed to be running.

```bash
sudo systemctl status php8.5-fpm
```

Expected:

```text
Active: active (running)
```

---

## Accessing the WordPress Installer

The website was accessed using the Ubuntu Server IP address.

Example:

```text
http://192.168.64.6
```

The WordPress installation page loaded successfully.

---

## Completing WordPress Setup

The following information was configured:

* Site title
* Administrator username
* Administrator password
* Email address

After installation, the WordPress dashboard became accessible.

Admin panel:

```text
http://192.168.64.6/wp-admin
```

Website homepage:

```text
http://192.168.64.6
```

---

## Troubleshooting

During deployment, several issues were identified and resolved.

Examples:

* Database connectivity
* File ownership
* PHP-FPM socket configuration
* Nginx syntax validation
* WordPress configuration
* MariaDB user permissions

Each issue was diagnosed and corrected during the deployment process.

---

## Commands Used

```bash
sudo nano /etc/nginx/sites-available/wordpress

sudo ln -s /etc/nginx/sites-available/wordpress \
/etc/nginx/sites-enabled/

sudo rm /etc/nginx/sites-enabled/default

sudo nginx -t

sudo systemctl restart nginx

sudo systemctl status nginx

sudo systemctl status php8.5-fpm
```

---

## Skills Demonstrated

* Nginx virtual host configuration
* PHP-FPM integration
* Linux symbolic links
* Service management
* Configuration validation
* Troubleshooting
* WordPress deployment
* Web server administration

---

## Result

At the end of this phase:

* Nginx was configured for WordPress.
* PHP-FPM integration was completed.
* The virtual host was enabled.
* Configuration validation passed.
* Nginx was restarted successfully.
* WordPress installation was completed.
* The WordPress dashboard was accessible.
* The public website was accessible.
* The complete LEMP stack was operational.

---

## Screenshots

Suggested screenshots:

* Nginx virtual host configuration
* Nginx syntax test
* PHP-FPM service status
* WordPress installation page
* WordPress dashboard
* WordPress homepage
* Nginx service status
