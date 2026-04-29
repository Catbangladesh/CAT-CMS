
# CAT CMS (Next Gen Custom MVC & OpenLiteSpeed Based) 🐈
### "The High-Performance Open Source Hosting & ISP ERP"

**CAT CMS** is a lightweight, high-speed management ecosystem built with a **Custom MVC Architecture** and powered by the **OpenLiteSpeed** web server. It eliminates the overhead of heavy frameworks while providing enterprise-grade billing and server automation.

---

## 🚀 Why Custom MVC & OpenLiteSpeed?
- **Speed:** Zero framework overhead ensures lightning-fast execution.
- **Performance:** OpenLiteSpeed provides superior PHP processing via **LSAPI** and built-in **LSCache**.
- **Control:** Granular control over Linux system resources and service management.

## 🛠 Tech Stack
- **Language:** PHP 8.3+ (Pure MVC Pattern)
- **Web Server:** OpenLiteSpeed (OLS)
- **Database:** MariaDB (using PDO for security)
- **UI Base:** AdminLTE 4 (Bootstrap 5)
- **Template Engine:** BladeOne or Twig

## 📦 Installation
Optimized for **Ubuntu 22.04/24.04 LTS**.
```bash
curl -sSL https://catbangladesh.com | sudo bash
```

---

### ২. `docs/panel-logic.md` (OpenLiteSpeed Focus)

```markdown
# OpenLiteSpeed Control Logic 🖥️

This document explains how CAT CMS interacts with the OpenLiteSpeed (OLS) web server.

### 1. Web Server Integration
- **OLS Configuration:** The system generates XML-based VirtualHost configurations for OLS.
- **Listeners:** Automated management of Port 80 (HTTP) and Port 443 (HTTPS) listeners.
- **LSPHP:** Each user account will have its own **LSPHP External Application** profile to ensure process isolation and security.

### 2. Automation Tasks
- **VHost Creation:** Creating `/usr/local/lsws/conf/vhosts/domain_name.xml`.
- **Graceful Restart:** Triggering `killall -HUP lshttpd` to apply changes without downtime.
- **SSL:** Automated mapping of Let's Encrypt certificates to OLS listeners.
```

---

### ৩. `docs/architecture.md` (Custom MVC Structure)

```markdown
# Custom MVC Architecture 🏗️

CAT CMS follows a strict **Model-View-Controller** pattern to maintain clean and scalable code.

### Folder Structure:
- `/app`: Core logic (Controllers, Models, Middleware).
- `/config`: System and Database configuration files.
- `/public`: The only accessible directory (Index.php, Assets).
- `/routes`: Definition of URL mappings and request handling.
- `/views`: UI templates based on AdminLTE 4.

### Core Principles:
1. **Security:** All database queries must use **PDO Prepared Statements**.
2. **Routing:** A lightweight custom router handles all incoming requests.
3. **Services:** OS-level commands are executed via a secure System Service Layer.
```

---

### ৪. `ROADMAP.md` (Updated Milestones)

```markdown
# 🗺️ CAT CMS Roadmap

- [ ] **Phase 1:** Custom MVC Core setup & AdminLTE 4 UI integration.
- [ ] **Phase 2:** OpenLiteSpeed VirtualHost automation module.
- [ ] **Phase 3:** Core Billing & WHMCS-grade ERP engine.
- [ ] **Phase 4:** ISP Radius & Bandwidth Management module.
- [ ] **Phase 5:** Production-ready One-Click Installer for Ubuntu.
```

---

