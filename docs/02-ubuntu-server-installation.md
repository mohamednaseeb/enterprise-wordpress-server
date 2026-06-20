# Ubuntu Server Installation

## Objective

The objective of this phase was to deploy an Ubuntu Server virtual machine that would serve as the foundation for an enterprise-grade WordPress hosting environment.

## Environment

| Component               | Details                         |
| ----------------------- | ------------------------------- |
| Host Machine            | MacBook Air                     |
| Virtualization Platform | UTM                             |
| Guest Operating System  | Ubuntu Server                   |
| Purpose                 | Enterprise WordPress Web Server |

---

## Why Ubuntu Server?

Ubuntu Server was selected because it is a stable, widely adopted Linux distribution with long-term support (LTS). It is commonly used in production environments for web hosting, cloud computing, and enterprise infrastructure.

Key advantages include:

* Long-Term Support (LTS)
* Large community and documentation
* Strong package management with APT
* Excellent compatibility with Nginx, MariaDB, PHP, and WordPress

---

## Virtual Machine Creation

A virtual machine was created using UTM on macOS.

The VM was configured with:

* Ubuntu Server ISO image
* Allocated CPU and memory resources
* Virtual storage
* Network adapter for LAN connectivity

After configuration, the Ubuntu Server installation process was started.

---

## Ubuntu Server Installation

The Ubuntu Server installer was used to:

* Select language and keyboard layout
* Configure network settings
* Configure storage
* Create an administrator account
* Install the base operating system
* Install the OpenSSH server

After installation, the system rebooted into the newly installed Ubuntu Server environment.

---

## Initial System Verification

After the first login, basic system information was verified.

Commands used:

```bash
hostnamectl
ip addr
whoami
pwd
```

These commands confirmed:

* Server hostname
* Network interface configuration
* Current user
* Working directory

---

## System Update

The package index and installed packages were updated.

```bash
sudo apt update
sudo apt upgrade -y
```

Keeping the operating system updated ensures access to the latest security patches and software improvements.

---

## Result

At the end of this phase:

* Ubuntu Server was successfully installed.
* The virtual machine was operational.
* Administrative access was available.
* The system was fully updated.
* The server was ready for remote management and service installation.

---

## Skills Demonstrated

* Linux server deployment
* Virtual machine administration
* Ubuntu Server installation
* Package management
* Initial system configuration
* System verification

---

## Screenshots

Suggested screenshots:

* UTM virtual machine configuration
* Ubuntu Server installer
* First successful login
* System update process
* Network configuration

