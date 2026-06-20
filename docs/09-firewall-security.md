# Firewall and Basic Security Configuration

## Objective

The objective of this phase was to improve the security of the Ubuntu Server by configuring a firewall and reviewing essential security settings for the deployed web application.

Basic hardening measures help protect the server by limiting network exposure and restricting access to only required services.

---

## Environment

| Component        | Details                      |
| ---------------- | ---------------------------- |
| Operating System | Ubuntu Server                |
| Firewall         | UFW (Uncomplicated Firewall) |
| SSH Port         | 22                           |
| HTTP Port        | 80                           |
| Database Port    | 3306                         |

---

## Why Server Security Matters

A production server should expose only the services required for operation.

For this project:

* SSH provides remote administration.
* Nginx serves web traffic.
* MariaDB stores application data.

Limiting unnecessary network access reduces the attack surface of the server.

---

## What is UFW?

UFW (Uncomplicated Firewall) is a firewall management tool for Linux.

It provides a simple interface for managing firewall rules based on iptables.

UFW was selected because it is:

* Easy to configure
* Included with Ubuntu
* Suitable for production environments

---

## Checking Firewall Status

The firewall status was verified.

```bash
sudo ufw status
```

Initially, the firewall was inactive.

---

## Allowing SSH Access

Before enabling the firewall, SSH access was permitted.

```bash
sudo ufw allow OpenSSH
```

This prevents accidental loss of remote administrative access.

---

## Allowing Web Traffic

HTTP traffic was permitted.

```bash
sudo ufw allow 80/tcp
```

This allows users to access the WordPress website.

---

## Enabling the Firewall

After the required rules were configured, the firewall was enabled.

```bash
sudo ufw enable
```

The firewall activation was confirmed.

---

## Verifying Firewall Rules

Firewall rules were inspected.

```bash
sudo ufw status verbose
```

The configuration confirmed:

* SSH access allowed
* HTTP access allowed
* Incoming connections denied by default

---

## Reviewing SSH Security

The SSH configuration was inspected.

```bash
sudo grep -E "PermitRootLogin|PasswordAuthentication|PubkeyAuthentication" /etc/ssh/sshd_config
```

Current configuration:

* Root password login restricted
* Password authentication enabled
* Public key authentication supported

These settings provide a balance between usability and security for the project environment.

---

## Verifying the SSH Service

The SSH service was verified.

```bash
sudo systemctl status ssh
```

The service was active and operational.

---

## Verifying Open Network Ports

Open ports were inspected.

```bash
sudo ss -tulpn
```

Important services included:

| Service | Port |
| ------- | ---- |
| SSH     | 22   |
| HTTP    | 80   |
| MariaDB | 3306 |

---

## Database Security

MariaDB was verified to listen only on the local interface.

Example:

```text
127.0.0.1:3306
```

This prevents external systems from connecting directly to the database server.

---

## Verifying Running Services

Critical services were checked.

```bash
sudo systemctl status ssh
sudo systemctl status nginx
sudo systemctl status mariadb
sudo systemctl status php8.5-fpm
```

All required services were operational.

---

## Commands Used

```bash
sudo ufw status

sudo ufw allow OpenSSH

sudo ufw allow 80/tcp

sudo ufw enable

sudo ufw status verbose

sudo grep -E "PermitRootLogin|PasswordAuthentication|PubkeyAuthentication" /etc/ssh/sshd_config

sudo systemctl status ssh

sudo systemctl status nginx

sudo systemctl status mariadb

sudo systemctl status php8.5-fpm

sudo ss -tulpn
```

---

## Skills Demonstrated

* Linux firewall administration
* UFW configuration
* Service verification
* SSH security review
* Network port inspection
* Basic Linux hardening
* Service monitoring

---

## Result

At the end of this phase:

* UFW was configured successfully.
* SSH access was protected.
* HTTP traffic was permitted.
* Default firewall policies were applied.
* SSH security settings were reviewed.
* MariaDB network exposure was verified.
* Critical services were confirmed to be operational.
* Basic Linux server hardening was completed.

---

## Screenshots

Suggested screenshots:

* UFW status
* UFW verbose output
* SSH configuration review
* SSH service status
* Nginx service status
* MariaDB service status
* PHP-FPM service status
* Open ports using ss -tulpn
