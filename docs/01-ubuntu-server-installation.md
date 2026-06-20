# Ubuntu Server Installation

## Project Overview

This document describes the installation and initial configuration of the Ubuntu Server used for the Enterprise WordPress Server project.

The objective was to create a stable Linux server that could host a production-style WordPress environment using:

- Nginx
- MariaDB
- PHP-FPM
- OpenSSH
- UFW Firewall

---

## Environment

### Host Machine

- Hardware: MacBook Air
- Operating System: macOS

### Virtualization Platform

- UTM Virtual Machine

### Guest Operating System

- Ubuntu Server

---

## VM Configuration

| Resource | Allocation |
|----------|-----------|
| CPU | 4 Cores |
| Memory | 8 GB |
| Storage | 30 GB |
| Network | Bridged |

---

## Ubuntu Installation

The Ubuntu Server ISO image was installed inside a UTM virtual machine.

During installation:

- Language selected
- Keyboard configured
- Network configured
- Storage partitioned
- User account created
- SSH server installed
- System packages updated

---

## Initial System Verification

After installation, basic system information was verified.

### Check hostname

```bash
hostnamectl
```

### Check IP address

```bash
ip a
```

### Check disk usage

```bash
df -h
```

### Check memory

```bash
free -h
```

---

## System Update

The package repository was updated and installed packages upgraded.

```bash
sudo apt update
sudo apt upgrade -y
```

---

## Result

Ubuntu Server was successfully installed and configured.

The server was ready for:

- SSH remote administration
- Nginx installation
- Database installation
- PHP installation
- WordPress deployment

---

## Skills Demonstrated

- Ubuntu Server installation
- Virtual machine administration
- Linux command line
- System verification
- Package management
- Server preparation
