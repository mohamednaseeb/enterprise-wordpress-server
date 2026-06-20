# PHP and PHP-FPM Installation

## Objective

The objective of this phase was to install PHP and PHP-FPM on the Ubuntu Server to provide dynamic content processing for the WordPress application.

PHP is the scripting language used by WordPress, while PHP-FPM (FastCGI Process Manager) efficiently handles PHP requests from the Nginx web server.

---

## Environment

| Component           | Details       |
| ------------------- | ------------- |
| Operating System    | Ubuntu Server |
| PHP Version         | PHP 8.5       |
| PHP Process Manager | PHP-FPM       |
| Web Server          | Nginx         |
| Application         | WordPress     |

---

## What is PHP?

PHP is a server-side scripting language widely used for web development.

WordPress is primarily written in PHP and relies on it to:

* Generate dynamic web pages
* Process user requests
* Connect to the database
* Manage authentication
* Handle plugins and themes

---

## What is PHP-FPM?

PHP-FPM (FastCGI Process Manager) is responsible for executing PHP scripts efficiently.

Instead of Nginx processing PHP directly, requests are forwarded to PHP-FPM through a Unix socket.

Architecture:

```text
Client
   |
Nginx
   |
PHP-FPM
   |
WordPress
   |
MariaDB
```

---

## Installing PHP

The required PHP packages and WordPress dependencies were installed.

```bash
sudo apt update

sudo apt install php-fpm php-mysql php-cli php-curl php-gd \
php-mbstring php-xml php-zip php-intl php-bcmath \
php-imagick unzip -y
```

Installation completed successfully.

---

## Verifying the PHP Installation

The installed PHP version was checked.

```bash
php -v
```

Example output:

```
PHP 8.5.x
```

This confirmed that PHP was installed correctly.

---

## Verifying PHP-FPM

The PHP-FPM service was checked.

```bash
sudo systemctl status php8.5-fpm
```

Expected output:

```
Active: active (running)
```

This confirmed that the PHP FastCGI Process Manager was operational.

---

## Enabling PHP-FPM at Boot

PHP-FPM was configured to start automatically after system reboot.

```bash
sudo systemctl enable php8.5-fpm
```

---

## Verifying the PHP Socket

PHP-FPM communicates with Nginx using a Unix socket.

Verification:

```bash
ls /run/php/
```

Example:

```
php8.5-fpm.sock
```

The socket file confirmed that PHP-FPM was ready to receive requests.

---

## Verifying PHP Modules

Installed PHP modules were checked.

```bash
php -m
```

Important modules for WordPress included:

* curl
* gd
* imagick
* intl
* mbstring
* mysqli
* mysqlnd
* PDO
* pdo_mysql
* xml
* xmlreader
* xmlwriter
* zip

These modules provide functionality required by WordPress and many plugins.

---

## Managing the PHP-FPM Service

Start PHP-FPM:

```bash
sudo systemctl start php8.5-fpm
```

Stop PHP-FPM:

```bash
sudo systemctl stop php8.5-fpm
```

Restart PHP-FPM:

```bash
sudo systemctl restart php8.5-fpm
```

Check service status:

```bash
sudo systemctl status php8.5-fpm
```

---

## Commands Used

```bash
sudo apt update

sudo apt install php-fpm php-mysql php-cli php-curl php-gd \
php-mbstring php-xml php-zip php-intl php-bcmath \
php-imagick unzip -y

php -v

sudo systemctl status php8.5-fpm

sudo systemctl enable php8.5-fpm

ls /run/php/

php -m
```

---

## Skills Demonstrated

* Linux package management
* PHP installation
* PHP-FPM administration
* Service management
* Unix socket verification
* Dependency management
* WordPress environment preparation

---

## Result

At the end of this phase:

* PHP 8.5 was successfully installed.
* PHP-FPM was operational.
* Automatic service startup was configured.
* Required WordPress PHP modules were installed.
* PHP-FPM socket communication was verified.
* The server was prepared for WordPress deployment.

---

## Screenshots

Suggested screenshots:

* PHP installation
* PHP version verification
* PHP-FPM service status
* PHP socket verification
* Installed PHP modules
* PHP-FPM running successfully
