# 🗺️ CAT CMS Development Roadmap

This roadmap outlines the development stages of **CAT CMS**. Our goal is to build the most stable and feature-rich open-source Hosting & ISP management ecosystem.

--- 

## 🏁 Phase 1: Foundation & Core ERP (Month 1-2)
*Focus: Setting up the Laravel environment and Billing Logic.*

- [ ] **Architecture Setup:** Initialize Laravel 11 with AdminLTE 4 (Bootstrap 5).
- [ ] **Authentication:** Multi-auth system for Admins, Support Staff, and Clients.
- [ ] **Database Core:** Implement the primary schema for Users, Products, and Invoices.
- [ ] **Billing Engine:** Automated invoice generation and recurring billing logic.
- [ ] **Local Gateways:** Integration of bKash, Nagad, and SSLCommerz.

## ⚙️ Phase 2: Server Bridge & Control Panel (Month 3-4)
*Focus: Connecting the web interface with the Linux OS.*

- [ ] **System Daemon:** Develop the secure bridge (cat-daemon) to execute root commands.
- [ ] **Webstack Automation:** One-click Nginx VirtualHost & PHP-FPM pool creation.
- [ ] **Database Management:** Automated MariaDB/MySQL user and DB creation.
- [ ] **Security:** Integration of Let's Encrypt (SSL) and Firewall management (UFW).
- [ ] **File Manager:** A web-based file explorer for hosted websites.

## 📡 Phase 3: ISP & Radius Integration (Month 5-6)
*Focus: Specialized tools for Internet Service Providers.*

- [ ] **Radius Sync:** Integration with FreeRadius for PPPoE and Hotspot management.
- [ ] **Bandwidth Control:** Real-time speed limiting and data capping logic.
- [ ] **MikroTik Integration:** API-based communication for automated provisioning.
- [ ] **User Monitoring:** Real-time bandwidth usage graphs and session logs.

## 🚀 Phase 4: Automation & Distribution (Month 7+)
*Focus: Scaling and making it production-ready for the world.*

- [ ] **One-Click Installer:** A robust Shell Script (`install.sh`) for fresh Ubuntu/AlmaLinux.
- [ ] **Remote Backups:** S3, Google Drive, and FTP backup automation.
- [ ] **REST API:** Full API documentation for external integrations and mobile apps.
- [ ] **Addon Marketplace:** Support for community-driven plugins and themes.

---

## 📈 Status Key
- 🏗️ **In Progress:** Features currently being coded.
- ✅ **Completed:** Features merged into the `main` branch.
- 🕒 **Planned:** Upcoming features in the queue.

---
*Note: This roadmap is subject to change based on community feedback and contribution priorities.*
