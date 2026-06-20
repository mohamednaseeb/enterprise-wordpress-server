# SSH Configuration

## Objective

The objective of this phase was to configure Secure Shell (SSH) on the Ubuntu Server to enable secure remote administration from the host machine.

SSH provides encrypted communication between systems and is the standard method for remotely managing Linux servers.

---

## Environment

| Component              | Details                |
| ---------------------- | ---------------------- |
| Host Machine           | MacBook Air            |
| Guest Machine          | Ubuntu Server (UTM VM) |
| Remote Access Protocol | SSH                    |
| SSH Server             | OpenSSH                |

---

## What is SSH?

Secure Shell (SSH) is a cryptographic network protocol used to securely connect to remote systems over a network.

SSH allows administrators to:

* Remotely manage Linux servers
* Execute commands securely
* Transfer files between systems
* Configure and monitor services
* Perform maintenance without physical access

---

## Installing OpenSSH Server

The OpenSSH Server package was installed using the APT package manager.

```bash
sudo apt update
sudo apt install openssh-server -y
```

---

## Verifying SSH Installation

After installation, the SSH service was checked to ensure it was running correctly.

```bash
sudo systemctl status ssh
```

Expected output:

```
Active: active (running)
```

This confirmed that the SSH daemon was operational.

---

## Identifying the Server IP Address

The Ubuntu Server IP address was identified to establish a remote connection.

```bash
hostname -I
```

or

```bash
ip addr
```

Example:

```
192.168.64.6
```

---

## Connecting from macOS

The Ubuntu Server was accessed remotely from the MacBook using the SSH client.

```bash
ssh mohamed@192.168.64.6
```

During the first connection, SSH requested confirmation of the server's authenticity.

```
Are you sure you want to continue connecting (yes/no)?
```

Typing:

```
yes
```

added the server fingerprint to the known hosts file.

The user's password was then entered to establish the connection.

---

## Verifying the Remote Session

After connecting successfully, several commands were executed to verify the session.

```bash
whoami
hostname
pwd
```

These commands confirmed:

* Logged-in user
* Server hostname
* Current working directory

---

## Verifying the SSH Listening Port

The listening ports on the server were inspected.

```bash
sudo ss -tulpn | grep :22
```

Output confirmed that SSH was listening on port 22.

---

## Reviewing Basic SSH Security Settings

The SSH configuration file was inspected.

```bash
sudo grep -E "PermitRootLogin|PasswordAuthentication|PubkeyAuthentication" /etc/ssh/sshd_config
```

Current configuration:

```
PermitRootLogin prohibit-password
PasswordAuthentication yes
PubkeyAuthentication yes
```

These settings provide:

* Restricted root login
* Password-based authentication
* Support for SSH key authentication

---

## Commands Used

```bash
sudo apt update
sudo apt install openssh-server -y
sudo systemctl status ssh
hostname -I
ip addr
ssh mohamed@192.168.64.6
whoami
hostname
pwd
sudo ss -tulpn | grep :22
sudo grep -E "PermitRootLogin|PasswordAuthentication|PubkeyAuthentication" /etc/ssh/sshd_config
```

---

## Skills Demonstrated

* Linux package management
* Service management with systemd
* Remote Linux administration
* Network connectivity verification
* SSH client and server configuration
* Basic Linux security practices

---

## Result

At the end of this phase:

* OpenSSH Server was installed.
* The SSH service was active and running.
* The Ubuntu Server could be accessed remotely from macOS.
* The SSH listening port was verified.
* Basic SSH security settings were reviewed.
* Secure remote administration was successfully established.

---

## Screenshots

Suggested screenshots for this section:

* OpenSSH installation
* SSH service status
* SSH connection from macOS Terminal
* SSH listening on port 22
* SSH configuration verification
