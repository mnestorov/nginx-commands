# Nginx Commands

![Licence](https://img.shields.io/badge/Unlicense-red)

## Overview

These list of Nginx commands should help you better understand and manage Nginx commands based on their functionality.

## Starting and Stopping Nginx

- [Start Nginx](#start-nginx)
- [Stop Nginx](#stop-nginx)
- [Restart Nginx](#restart-nginx)
- [Reload Nginx](#reload-nginx)
- [Quit Nginx](#quit-nginx)
- [Check Nginx status](#check-nginx-status)

## Configuration Management

- [Reload Nginx configuration](#reload-nginx-configuration)
- [Test Nginx configuration for syntax errors](#test-nginx-configuration-for-syntax-errors)
- [Start Nginx with a custom configuration file](#start-nginx-with-a-custom-configuration-file)
- [Start Nginx with a custom error log file](#start-nginx-with-a-custom-error-log-file)
- [Start Nginx with a custom global configuration prefix](#start-nginx-with-a-custom-global-configuration-prefix)
- [Set a custom worker process count](#set-a-custom-worker-process-count)

## Logging and Monitoring

- [View Nginx error logs](#view-nginx-error-logs)
- [View Nginx access logs](#view-nginx-access-logs)
- [Display active Nginx connections](#display-active-nginx-connections)

## Process Management

- [Display Nginx process ID (PID)](#display-nginx-process-id-pid)
- [Send a signal to a specific Nginx process](#send-a-signal-to-a-specific-nginx-process)

## Boot Configuration

- [Enable Nginx auto-start at boot](#enable-nginx-auto-start-at-boot)
- [Disable Nginx auto-start at boot](#disable-nginx-auto-start-at-boot)

## Help and Version Information

- [Display Nginx version and configuration options](#display-nginx-version-and-configuration-options)
- [Display help information](#display-help-information)

## Configuration File Management

- [Create a temporary backup of the Nginx configuration](#create-a-temporary-backup-of-the-nginx-configuration)
- [Restore a backup of the Nginx configuration](#restore-a-backup-of-the-nginx-configuration)
- [Open the main Nginx configuration file with a text editor](#open-the-main-nginx-configuration-file-with-a-text-editor)
- [Open a specific server block configuration file with a text editor](#open-a-specific-server-block-configuration-file-with-a-text-editor)
- [Create a symbolic link to enable a server block](#create-a-symbolic-link-to-enable-a-server-block)
- [Remove a symbolic link to disable a server block](#remove-a-symbolic-link-to-disable-a-server-block)

---

## Starting and Stopping Nginx

### Start Nginx

```
sudo nginx
```

**For systemd (Ubuntu 16.04 LTS and above):**

```
sudo systemctl start nginx
```

### Stop Nginx

Stopping Nginx will kill all system processes quickly. This will terminate Nginx even if there are open connections. 
In order to do so, run one of the following commands:

```
sudo nginx -s stop
```

**For systemd (Ubuntu 16.04 LTS and above):**

```
sudo systemctl stop nginx
```

### Restart Nginx

```
sudo service nginx restart
```

**For systemd (Ubuntu 16.04 LTS and above):**

```
sudo systemctl restart nginx
```

### Reload Nginx

```
sudo nginx -s reload
```

**For systemd (Ubuntu 16.04 LTS and above):**

```
sudo systemctl reload nginx
```

### Quit Nginx

```
sudo nginx -s quit
```

### Check Nginx status

```
sudo service nginx status
```

**For systemd (Ubuntu 16.04 LTS and above):**

```
sudo systemctl status nginx
```

## Configuration Management

### Reload Nginx configuration

```
sudo nginx -s reload
```

**For systemd (Ubuntu 16.04 LTS and above):**

```
sudo systemctl reload nginx
```

### Test Nginx configuration for syntax errors

```
sudo nginx -t
```

### Start Nginx with a custom configuration file

```
sudo nginx -c /path/to/custom/nginx.conf
```

### Start Nginx with a custom error log file

```
sudo nginx -e /path/to/custom/error.log
```

### Start Nginx with a custom global configuration prefix

```
sudo nginx -p /path/to/custom/prefix
```

### Set a custom worker process count

```
sudo nginx -g "worker_processes COUNT;"
```

## Logging and Monitoring

### View Nginx error logs

```
sudo tail -f /var/log/nginx/error.log
```

### View Nginx access logs

```
sudo tail -f /var/log/nginx/access.log
```

### Display active Nginx connections

```
sudo nginx -V 2>&1 | grep -o with-http_stub_status_module
```

## Process Management

### Display Nginx process ID (PID)

```
sudo cat /run/nginx.pid
```

### Send a signal to a specific Nginx process

```
sudo kill -s SIGNAL PID
```

## Boot Configuration

### Enable Nginx auto-start at boot

```
sudo systemctl enable nginx
```

### Disable Nginx auto-start at boot

```
sudo systemctl disable nginx
```

## Help and Version Information

### Display Nginx version and configuration options

```
nginx -V
```

### Display help information

```
nginx -h
```

## Configuration File Management

### Create a temporary backup of the Nginx configuration

```
sudo cp /etc/nginx/nginx.conf /etc/nginx/nginx.conf.backup
```

### Restore a backup of the Nginx configuration

```
sudo cp /etc/nginx/nginx.conf.backup /etc/nginx/nginx.conf
```

### Open the main Nginx configuration file with a text editor

```
sudo nano /etc/nginx/nginx.conf
```

### Open a specific server block configuration file with a text editor

```
sudo nano /etc/nginx/sites-available/your_server_block
```

### Create a symbolic link to enable a server block

```
sudo ln -s /etc/nginx/sites-available/your_server_block /etc/nginx/sites-enabled/
```

### Remove a symbolic link to disable a server block

```
sudo rm /etc/nginx/sites-enabled/your_server_block
```

---

## License

This repository is unlicense[d], so feel free to fork.
