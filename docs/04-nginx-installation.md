# Nginx Installation

## Objective

The objective of this phase was to install and configure the Nginx web server on the Ubuntu Server. Nginx serves as the front-end web server responsible for handling HTTP requests and delivering web content to clients.

Nginx was selected due to its high performance, reliability, and widespread use in production environments.

---

## Environment

| Component         | Details       |
| ----------------- | ------------- |
| Operating System  | Ubuntu Server |
| Web Server        | Nginx         |
| Default HTTP Port | 80            |
| Management Tool   | systemd       |

---

## What is Nginx?

Nginx is an open-source web server and reverse proxy designed for high performance and low resource consumption.

Common uses include:

* Hosting websites
* Serving static content
* Reverse proxy services
* Load balancing
* SSL/TLS termination

Nginx is commonly deployed alongside PHP-FPM for hosting WordPress applications.

---

## Installing Nginx

The package index was updated before installing Nginx.

```bash
sudo apt update
sudo apt install nginx -y
```

The installation completed successfully without errors.

---

## Verifying the Nginx Service

After installation, the Nginx service was checked.

```bash
sudo systemctl status nginx
```

Expected output:

```
Active: active (running)
```

This confirmed that the Nginx service was operational.

---

## Enabling Nginx at Boot

To ensure Nginx starts automatically after a system reboot, the service was enabled.

```bash
sudo systemctl enable nginx
```

---

## Verifying the Listening Port

The listening ports were inspected.

```bash
sudo ss -tulpn | grep :80
```

Output confirmed that Nginx was listening on TCP port 80.

---

## Testing the Web Server

The Nginx installation was tested locally.

```bash
curl http://localhost
```

The command returned the default Nginx welcome page.

The web server was also tested using a web browser by visiting the Ubuntu Server IP address.

Example:

```
http://192.168.64.6
```

The default Nginx landing page was displayed successfully.

---

## Managing the Nginx Service

Common service management commands:

Start Nginx:

```bash
sudo systemctl start nginx
```

Stop Nginx:

```bash
sudo systemctl stop nginx
```

Restart Nginx:

```bash
sudo systemctl restart nginx
```

Reload configuration:

```bash
sudo systemctl reload nginx
```

Check status:

```bash
sudo systemctl status nginx
```

---

## Commands Used

```bash
sudo apt update
sudo apt install nginx -y
sudo systemctl status nginx
sudo systemctl enable nginx
sudo ss -tulpn | grep :80
curl http://localhost
sudo systemctl restart nginx
```

---

## Skills Demonstrated

* Linux package management
* Nginx installation
* Service management using systemd
* Port verification
* Local web server testing
* Basic web server administration

---

## Result

At the end of this phase:

* Nginx was successfully installed.
* The service was active and running.
* Nginx was configured to start automatically at boot.
* The server was listening on HTTP port 80.
* The default Nginx webpage was accessible from both the terminal and a web browser.
* The Ubuntu Server was ready to host web applications.

---

## Screenshots

Suggested screenshots for this section:

* Nginx installation
* Nginx service status
* Port 80 verification
* Output of `curl http://localhost`
* Default Nginx webpage in a browser
