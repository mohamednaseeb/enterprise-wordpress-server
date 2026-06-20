# Final Verification and Project Summary

## Objective

The objective of this phase was to verify that all components of the Enterprise WordPress Server were functioning correctly and that the complete LEMP stack was operational.

This validation confirmed successful deployment of the Ubuntu Server, web server, database server, PHP environment, WordPress application, and basic security configuration.

---

## Project Architecture

The completed infrastructure consists of the following components:

```text
MacBook Air
      │
      │ SSH
      ▼
Ubuntu Server (UTM)
      │
      ├── OpenSSH
      ├── UFW Firewall
      ├── Nginx
      ├── PHP-FPM
      ├── MariaDB
      └── WordPress
```

Each component was configured and tested individually before integration into the complete system.

---

## Service Verification

Critical services were verified.

### SSH

```bash
sudo systemctl status ssh
```

Status:

* Active
* Running

---

### Nginx

```bash
sudo systemctl status nginx
```

Status:

* Active
* Running

---

### MariaDB

```bash
sudo systemctl status mariadb
```

Status:

* Active
* Running

---

### PHP-FPM

```bash
sudo systemctl status php8.5-fpm
```

Status:

* Active
* Running

---

## Network Verification

Listening services were verified.

```bash
sudo ss -tulpn
```

Important ports:

| Service | Port |
| ------- | ---- |
| SSH     | 22   |
| HTTP    | 80   |
| MariaDB | 3306 |

MariaDB was confirmed to listen only on the local interface.

---

## Firewall Verification

Firewall configuration was validated.

```bash
sudo ufw status verbose
```

Rules confirmed:

* SSH allowed
* HTTP allowed
* Incoming traffic denied by default

---

## Database Verification

The WordPress database was confirmed.

```sql
SHOW DATABASES;
```

The dedicated WordPress database was present.

Database users and permissions were verified.

---

## WordPress Verification

The WordPress installer completed successfully.

Public website:

```text
http://SERVER_IP
```

Administrator dashboard:

```text
http://SERVER_IP/wp-admin
```

Both interfaces were accessible and operational.

---

## Remote Administration Verification

Remote administration from macOS was tested.

```bash
ssh username@SERVER_IP
```

The SSH connection was established successfully.

---

## LEMP Stack Validation

The complete LEMP stack was verified.

```text
Linux
   │
Nginx
   │
PHP-FPM
   │
WordPress
   │
MariaDB
```

All components communicated successfully.

---

## Technologies Used

* Ubuntu Server
* UTM Virtual Machine
* OpenSSH
* Nginx
* MariaDB
* PHP 8.5
* PHP-FPM
* WordPress
* UFW Firewall
* Git
* GitHub

---

## Skills Demonstrated

### Linux Administration

* Ubuntu Server deployment
* Package management
* Service management
* User and permission management

### Networking

* IP configuration
* Port verification
* Remote access
* Service connectivity

### Web Server Administration

* Nginx installation
* Virtual host configuration
* PHP-FPM integration

### Database Administration

* MariaDB installation
* Database creation
* User management
* Privilege assignment

### Application Deployment

* WordPress installation
* Configuration
* File management

### Security

* UFW firewall
* SSH review
* Service verification
* Database exposure validation

### Version Control

* Git
* GitHub
* Repository management
* Project documentation

---

## Challenges Encountered

During the project several issues were identified and resolved, including:

* SSH connectivity
* Nginx configuration
* MariaDB permissions
* WordPress database connection
* PHP-FPM integration
* File ownership and permissions
* Firewall configuration
* Git and GitHub synchronization

Troubleshooting these issues improved practical Linux administration skills.

---

## Project Outcome

The project objectives were successfully achieved.

The completed server provides:

* Secure remote administration
* Web application hosting
* Database services
* Dynamic PHP processing
* WordPress content management
* Basic firewall protection

The Enterprise WordPress Server is fully operational and demonstrates practical Linux system administration and web server deployment skills.

---

## Conclusion

This project provided practical experience in deploying and managing a complete LEMP stack on Ubuntu Server.

By manually installing and configuring each component, valuable experience was gained in Linux administration, networking, web server management, database administration, security, troubleshooting, and infrastructure documentation.

The completed project serves as a portfolio example of a production-style WordPress deployment and demonstrates foundational skills relevant to Linux System Administration and DevOps roles.

---

## Suggested Screenshots

* SSH connection
* UFW status
* Nginx service
* MariaDB service
* PHP-FPM service
* Open ports
* WordPress homepage
* WordPress dashboard
* GitHub repository
* Final project architecture
