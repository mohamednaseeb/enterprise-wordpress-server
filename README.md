# Enterprise WordPress Server Deployment

## Project Overview

This project demonstrates the deployment of a production-style WordPress server on Ubuntu using the LEMP stack.

The infrastructure was built from scratch inside a UTM virtual machine running on macOS and configured entirely through the Linux command line.

The project includes:

* Ubuntu Server
* OpenSSH
* Nginx
* MariaDB
* PHP 8.5
* PHP-FPM
* WordPress
* UFW Firewall
* Git and GitHub documentation

---

# Project Architecture

```
                Client
                   |
                   |
             HTTP / SSH
                   |
                   |
          Ubuntu Server
                   |
      +------------+------------+
      |            |            |
    SSH         Nginx      UFW Firewall
                   |
               PHP-FPM
                   |
              WordPress
                   |
               MariaDB
```

---

# Technologies Used

| Technology    | Purpose               |
| ------------- | --------------------- |
| Ubuntu Server | Operating System      |
| UTM           | Virtualization        |
| OpenSSH       | Remote Administration |
| Nginx         | Web Server            |
| MariaDB       | Database              |
| PHP 8.5       | Dynamic Content       |
| PHP-FPM       | PHP Processing        |
| WordPress     | Content Management    |
| UFW           | Firewall              |
| Git           | Version Control       |
| GitHub        | Documentation         |

---

# Project Objectives

* Deploy Ubuntu Server
* Configure SSH remote administration
* Install Nginx
* Install MariaDB
* Install PHP and PHP-FPM
* Deploy WordPress
* Configure Nginx virtual host
* Configure firewall rules
* Verify the complete LEMP stack
* Document the entire deployment process

---

# Documentation

| Chapter | Description                       |
| ------- | --------------------------------- |
| 01      | Project Overview                  |
| 02      | Ubuntu Server Installation        |
| 03      | SSH Configuration                 |
| 04      | Nginx Installation                |
| 05      | MariaDB Installation              |
| 06      | PHP and PHP-FPM Installation      |
| 07      | WordPress Installation            |
| 08      | Nginx and WordPress Configuration |
| 09      | Firewall and Basic Security       |
| 10      | Final Verification                |

---

# Skills Demonstrated

## Linux Administration

* Ubuntu Server
* Package Management
* Service Management
* User and Permission Management

## Networking

* IP Addressing
* Port Verification
* SSH Remote Access

## Web Server Administration

* Nginx
* Virtual Hosts
* PHP-FPM Integration

## Database Administration

* MariaDB Installation
* Database Creation
* User Management
* SQL Privileges

## Application Deployment

* WordPress Installation
* Configuration
* File Permissions

## Security

* UFW Firewall
* SSH Review
* Basic Server Hardening

## Version Control

* Git
* GitHub
* Documentation

---

# Verification

The following services were successfully deployed and tested.

| Service      | Status |
| ------------ | ------ |
| SSH          | ✅      |
| Nginx        | ✅      |
| MariaDB      | ✅      |
| PHP-FPM      | ✅      |
| WordPress    | ✅      |
| UFW Firewall | ✅      |

---

# Project Outcome

The completed project provides:

* Secure remote administration
* Dynamic web hosting
* Database services
* WordPress content management
* Basic server security
* Practical Linux administration experience

---

# Learning Outcomes

This project provided hands-on experience with:

* Linux System Administration
* Networking
* Nginx
* MariaDB
* PHP
* WordPress
* Firewall Configuration
* Service Management
* Troubleshooting
* Git and GitHub

---

# Author

**Mohamed Naseeb**

Junior Linux System Administrator | DevOps Enthusiast

GitHub:
https://github.com/mohamednaseeb
