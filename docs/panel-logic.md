# Server Control Logic (OpenLiteSpeed Native) 🖥️

This document outlines the core logic for managing the Linux server and OpenLiteSpeed (OLS) web server through the CAT CMS Custom MVC framework.

## 1. Web Server Architecture
CAT CMS uses **OpenLiteSpeed** as the primary web engine. Unlike Nginx, OLS configuration is primarily XML-based and uses the high-performance **LSAPI** for PHP processing.

### Key Components:
- **Binary Location:** `/usr/local/lsws/bin/lshttpd`
- **Config Path:** `/usr/local/lsws/conf/vhosts/`
- **PHP Handler:** LSPHP 8.3 (Integrated via LSAPI)

## 2. VirtualHost Automation Logic
When a client adds a domain, the system must perform the following:
1. **Directory Creation:** Create a dedicated web root at `/var/www/vhosts/{username}/{domain_name}/public_html`.
2. **Template Mapping:** Generate a new `.xml` configuration file based on a pre-defined OLS VHost template.
3. **Graceful Restart:** Trigger a smooth reload of OLS to apply changes without dropping active connections:
   ```bash
   # Command to be triggered via PHP System Call
   /usr/local/lsws/bin/lswsctrl restart
   ```

## 3. User & Resource Isolation
To ensure maximum security and cPanel-like isolation:
- **Individual System Users:** Every hosting account must be mapped to a unique Linux system user.
- **LSPHP External App:** Each VirtualHost will have its own External Application profile. This ensures that a script on one site cannot access another site's files (Open_basedir protection).

## 4. Automation Modules
### 🔐 SSL Management (Let's Encrypt)
- The system will trigger `certbot` to generate SSL certificates.
- Automated mapping of the `.crt` and `.key` files into the OLS VirtualHost Listener settings.

### 🛡️ Security & Firewall
- **Port Management:** UI-driven management of ports using `UFW` or `CSF`.
- **ModSecurity:** Enabling/Disabling the Web Application Firewall (WAF) directly from the panel.

### 💾 Database Management
- Automated creation of MariaDB databases and users via the **PDO** layer.
- Privilege management (GRANT/REVOKE) for specific DB users.

## 5. System Bridge (The Secure Execution)
Since the web server runs as `lsphp`, it cannot execute `root` commands directly. 
- **The Wrapper Logic:** CAT CMS will use a secure wrapper or a sudoers-allowed script to execute specific system tasks like restarting services or modifying `/etc/hosts`.

---
*Note: All OS-level commands must be sanitized to prevent Command Injection vulnerabilities.*
