# CAT CMS (Linux-Native Control Panel & Billing) 🐈
### "Where Infrastructure meets Business Automation"

**CAT CMS** is a specialized Linux distribution-independent management layer. It integrates a **high-performance web control panel** with a **native billing & ERP engine**, allowing providers to manage Bare Metal or VPS instances and their customers in one unified ecosystem.

---

## 🛠 System Architecture (The "CAT" Engine)
Unlike traditional panels, CAT CMS uses a **Hybrid Bridge** to communicate with the Linux OS:

1.  **Application Layer:** Laravel 11 (Managing Business Logic, API, and UI).
2.  **Service Layer:** A dedicated System-Daemon (written in Go or Python) that runs with `root` privileges to execute OS commands.
3.  **Communication:** Secure Local Socket / Encrypted API calls between Laravel and the System-Daemon.

## 🏗 Key Components
### 🖥 The Controller (Panel Features)
- **Webstack:** Nginx (Reverse Proxy) + Apache/LiteSpeed (Backend).
- **DNS:** Integrated PowerDNS or Bind management.
- **Security:** ModSecurity, CSF (ConfigServer Firewall), and automated Let’s Encrypt.
- **Virtualization:** Support for KVM/LXC management (future roadmap).

### 💰 The Engine (Billing & ISP Features)
- **ISP Module:** Radius Server integration for bandwidth management and PPPoE/Hotspot.
- **Billing:** Dynamic tax rules, pro-rata billing, and automated service suspension.
- **Gateways:** Native integration for **bKash, Nagad, Upay, SSLCommerz, Stripe, and PayPal**.

### 📦 OS Native Setup
One-command installation for **Ubuntu 22.04/24.04** and **AlmaLinux 9**:
```bash
curl -sSL https://catcms.org | bash
```

---

## 🗺 Roadmap & Milestones
- [ ] **Alpha:** Laravel-based Dashboard & Database Schema for Multi-tenant users.
- [ ] **Beta:** Integration of `systemctl` commands via PHP-SSH for Nginx management.
- [ ] **Stable:** Full automated billing cycle with ISP bandwidth control.

## 🤝 Contribution Guide
I am the Project Lead with domain expertise in ISP & Hosting. I am inviting:
- **Laravel Experts:** For the core ERP and API architecture.
- **System Programmers:** To build the `cat-daemon` for OS-level execution.
- **Linux Admins:** For server hardening and stack optimization.

---
### 💬 Why CAT CMS?
Because managing a hosting business shouldn't require 5 different subscriptions. **CAT CMS is the cPanel + WHMCS killer.**
