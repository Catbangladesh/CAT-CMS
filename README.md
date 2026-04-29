# 🐈 CAT CMS (Next-Gen ISP & Hosting ERP)

### *"Custom MVC Powered | OpenLiteSpeed Optimized | Linux Native"*

**CAT CMS** is a high-performance management layer that functions as both a **Web Control Panel** and a **Billing & ERP Engine**. It is specifically designed for providers to manage Bare Metal, VPS, Shared Hosting, and ISP operations within a single unified ecosystem.

---

## 🛠 System Architecture (The "CAT" Logic)
We have moved away from heavy frameworks to a **Custom Lightweight MVC Architecture** to ensure minimum memory footprint and maximum execution speed.

1.  **Application Layer:** Native PHP MVC (Custom Built for speed, security, and low overhead).
2.  **Web Server:** Native optimization for **OpenLiteSpeed** (LSCache, HTTP/3, and event-driven performance).
3.  **Service Layer:** A dedicated system daemon (`cat-daemon`) written in Go/Python that executes backend commands with `root` privileges.
4.  **Security:** Hacker-grade security enforcement operating directly at the kernel and firewall levels.

---

## 🏗 Key Components

### 🖥 The Controller (Infrastructure)
- **Webstack:** **OpenLiteSpeed** (Primary) + Nginx (Optional Reverse Proxy).
- **Virtualization:** Native support for KVM/LXC management (Roadmap).
- **Multi-Tenancy:** Strict resource isolation for Shared, Reseller, and Dedicated environments.
- **DNS & SSL:** PowerDNS integration and automated Wildcard SSL via Let's Encrypt.

### 💰 The Engine (ISP & Business Automation)
- **ISP Module:** Radius Server and MikroTik API integration (Bandwidth control, PPPoE, Hotspot management).
- **Billing:** Dynamic tax rules, pro-rata invoicing, and automated service suspension.
- **Local Gateways:** Native support for **bKash, Nagad, Upay,SurjoPay, and SSLCommerz**.
- **Global Gateways:** Stripe,PayPal & others Gateways integration 

---

## 🗺 Roadmap & Milestones
- [ ] **Phase 1 (Alpha):** Custom MVC Core Development & Database Schema.
- [ ] **Phase 2 (Beta):** OpenLiteSpeed Virtual Host automation & OLS API integration.
- [ ] **Phase 3 (Stable):** Full ISP Billing cycle with Radius/MikroTik automation.

---

## 📦 OS Native Setup
One-command installation for **Ubuntu 22.04/24.04** and **AlmaLinux 9**:

```bash
curl -sSL [https://catbangladesh.com/install.sh](https://catbangladesh.com/install.sh) | sudo bash
