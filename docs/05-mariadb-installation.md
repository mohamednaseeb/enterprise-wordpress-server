# MariaDB Installation and Configuration

## Objective

The objective of this phase was to install and configure MariaDB as the database management system for the WordPress server.

MariaDB provides the backend storage for WordPress, including website content, user accounts, posts, pages, comments, and configuration data.

---

## Environment

| Component        | Details       |
| ---------------- | ------------- |
| Operating System | Ubuntu Server |
| Database Server  | MariaDB       |
| Default Port     | 3306          |
| Service Manager  | systemd       |

---

## What is MariaDB?

MariaDB is an open-source relational database management system (RDBMS).

It is a community-developed fork of MySQL and is widely used for:

* Web applications
* Content management systems
* Enterprise databases
* Cloud applications

WordPress officially supports MariaDB and MySQL.

---

## Installing MariaDB

The package index was updated before installation.

```bash
sudo apt update
sudo apt install mariadb-server -y
```

The installation completed successfully.

---

## Verifying the MariaDB Service

After installation, the MariaDB service was checked.

```bash
sudo systemctl status mariadb
```

Expected output:

```
Active: active (running)
```

This confirmed that the database server was operational.

---

## Enabling MariaDB at Boot

MariaDB was configured to start automatically after system reboot.

```bash
sudo systemctl enable mariadb
```

---

## Securing the Database Server

The MariaDB secure installation script was executed.

```bash
sudo mysql_secure_installation
```

The following security measures were applied:

* Root authentication configured.
* Anonymous users removed.
* Remote root login disabled.
* Test database removed.
* Privilege tables reloaded.

These steps improve the overall security of the database server.

---

## Accessing MariaDB

The database server was accessed using:

```bash
sudo mysql
```

Successful login displayed:

```
Welcome to the MariaDB monitor.
```

---

## Creating the WordPress Database

A dedicated database for WordPress was created.

```sql
CREATE DATABASE wordpress;
```

Verification:

```sql
SHOW DATABASES;
```

The new database appeared in the list.

---

## Creating a WordPress Database User

A dedicated database user was created for WordPress.

```sql
CREATE USER 'wordpress'@'localhost' IDENTIFIED BY 'your_password';
```

A separate user account improves security by avoiding the use of the root account.

---

## Granting Database Permissions

The WordPress user was granted full access to the WordPress database.

```sql
GRANT ALL PRIVILEGES ON wordpress.* TO 'wordpress'@'localhost';
```

Privileges were applied with:

```sql
FLUSH PRIVILEGES;
```

---

## Verifying Database Users

Database users were checked.

```sql
SELECT User, Host FROM mysql.user;
```

The output confirmed the presence of:

* root
* mariadb.sys
* mysql
* wordpress

---

## Verifying the Listening Port

The MariaDB service listens on port 3306.

Verification:

```bash
sudo ss -tulpn | grep 3306
```

This confirmed that the database service was active.

---

## Commands Used

```bash
sudo apt update
sudo apt install mariadb-server -y
sudo systemctl status mariadb
sudo systemctl enable mariadb
sudo mysql_secure_installation
sudo mysql
```

SQL commands:

```sql
CREATE DATABASE wordpress;

CREATE USER 'wordpress'@'localhost'
IDENTIFIED BY 'your_password';

GRANT ALL PRIVILEGES
ON wordpress.*
TO 'wordpress'@'localhost';

FLUSH PRIVILEGES;

SHOW DATABASES;

SELECT User, Host FROM mysql.user;
```

---

## Skills Demonstrated

* Linux package management
* Database server installation
* MariaDB administration
* Database creation
* User management
* Privilege assignment
* Basic SQL
* Service management
* Database security hardening

---

## Result

At the end of this phase:

* MariaDB was successfully installed.
* The database service was running.
* Automatic startup was enabled.
* Security hardening was completed.
* A dedicated WordPress database was created.
* A dedicated WordPress user account was created.
* Appropriate database permissions were assigned.
* The database server was ready for WordPress deployment.

---

## Screenshots

Suggested screenshots for this section:

* MariaDB installation
* MariaDB service status
* Running `sudo mysql`
* Creating the WordPress database
* Creating the WordPress user
* Granting privileges
* `SHOW DATABASES;`
* `SELECT User, Host FROM mysql.user;`
