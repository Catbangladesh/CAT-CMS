# Server Control Panel Logic 🖥️

This document outlines the interaction between the Laravel UI and the Linux System.

### 1. Web Stack Management
- **Nginx:** Automate VirtualHost creation (`/etc/nginx/sites-available`).
- **PHP-FPM:** Assign separate PHP pools for each user to ensure isolation.
- **Directories:** Websites should be stored in `/home/username/public_html`.

### 2. Security Execution
- **Permissions:** Each website must run under its own Linux User/Group.
- **Firewall:** Laravel UI will trigger commands to open/close ports (80, 443, 21, 22).
- **SSL:** Automated trigger for `certbot` (Let's Encrypt) when a domain is added.

### 3. Service Commands
- The UI should be able to: `start`, `stop`, `restart` services like Nginx, MySQL, and PHP-FPM securely.
