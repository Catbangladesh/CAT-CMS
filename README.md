[![Telegram Group](https://shields.io)](https://t.me/CATCMS_Global)
[![GitHub Stars](https://shields.io)](https://github.com)
[![License: MIT](https://shields.io)](https://opensource.org)

 # 🐈 CAT-CMS (Enterprise Cloud & ISP Ecosystem)

### *"Sovereign Infrastructure Automation | Single & Cluster Ready"*

**CAT-CMS** is a high-performance, Linux-native management layer that unifies **Web Hosting (Shared/VPS)** and **ISP Operations (Radius/MikroTik)** into a single, automated ecosystem. Developed by **Cyber Adversary Taskforce (CAT) Bangladesh**, it is engineered to eliminate dependency on expensive foreign licenses like cPanel and WHMCS, saving millions in foreign currency outflow.

---

## 🚀 Vision: Digital Sovereignty & Economic Impact
The primary mission of CAT-CMS is to achieve **Import Substitution**. Currently, thousands of USD flow out of Bangladesh every month for server management and billing licenses. CAT-CMS provides a locally-built, enterprise-grade alternative that is:
* **Cost Effective:** 0% licensing fee, keeping capital within the country.
* **Sovereign:** Securely managed by local engineers under national security standards.
* **Independent:** No more reliance on global price hikes of legacy panels.

---

## 🛠 High-Level Architecture (The Engine)
CAT-CMS follows a **Decoupled Hybrid Architecture** for maximum security and scalability.

1.  **Application Layer:** Symfony 7.x (Enterprise PHP Framework) — Handles Business Logic, Billing, API, and UI.
2.  **Data Layer:** PostgreSQL 16+ — Robust transactional integrity and GIS support for mapping.
3.  **Execution Layer:** `cat-daemon` (Golang) — A low-latency system agent running with root privileges to execute OS commands.
4.  **Web Server:** **OpenLiteSpeed** — Native event-driven architecture for ultra-fast web performance.

---

## 🏗 Directory & Project Structure
The project follows an industry-standard directory structure to ensure easy collaboration for developers:

```text
/cat-cms-project
├── app/                  # Symfony 7.x Core Logic
│   ├── config/           # YAML configs (Routes, DB, Security)
│   ├── src/              
│   │   ├── Controller/   # Dashboard & API Endpoints
│   │   ├── Entity/       # DB Models (Invoices, Users, Services)
│   │   ├── Service/      # Adapters for bKash, Mikrotik, OLS API
│   │   └── Command/      # Cron tasks (Auto-Suspension)
│   └── templates/        # Twig-based UI (Admin/Client Portals)
├── daemon/               # Golang System Agent (The Bridge)
│   ├── handlers/         # OS Task Execution (Systemctl, OLS)
│   ├── networking/       # Radius & IP Management Logic
│   └── main.go           # Daemon Entry point
├── provisioning/         # Deployment Automation
│   ├── cloud-init/       # Automated Install Script (install.sh)
│   └── packer/           # Custom Ubuntu ISO Build scripts
└── docs/                 # Swagger/OpenAPI Documentation

 ## ⚙️ Core Technical Logic & Workflows

**1. Automated Lifecycle & Billing**
​The system uses an advanced Pro-rata Billing Logic:
​Activation Flow: User pays via bKash/Nagad/Upay/SSLCommerz → Payment Hook triggers Symfony Service → API Signal sent to cat-daemon → Service Provisioned (vHost or Radius account).
​Suspension Logic: A daily Cron Job checks PostgreSQL for overdue invoices. If Current Date > Due Date, the system automatically triggers a suspension command across the Web Cluster or MikroTik Edge nodes.
**​2. Multi-Node Scaling (Single vs. Cluster)**
​Single-Server Mode: Full stack (Web, DB, Panel) on one node—ideal for small ISPs.
​Cluster Mode: A Master Node manages multiple Agent Nodes via encrypted mTLS communication, allowing for massive scaling across data centers.
​**3. GIS Network Mapping (Google Maps)**
​Built-in integration with Google Maps API allows ISP owners to:
​Visualize fiber optic POP locations.
​Monitor real-time client outages on a map.
​Optimize technician deployment based on client clusters.

## ​📦 Deployment: The "One-Command" Install
CAT-CMS is designed to be installed via Cloud-init or a simple Bash script on a fresh Ubuntu 24.04 LTS server.
curl -sSL [https://catbangladesh.com/install.sh](https://catbangladesh.com/install.sh) | sudo bash


## 💰 Why Choose CAT-CMS? (The Import Substitution Factor)

The primary goal of CAT-CMS is to eliminate the heavy reliance on expensive foreign software licenses. Below is a direct comparison of why CAT-CMS is the superior choice for the local and global market:

| Feature | Legacy Foreign Stack (cPanel + WHMCS + Virtualizor) | CAT-CMS Enterprise Ecosystem |
| :--- | :--- | :--- |
| **Monthly Licensing** | $100 - $250+ USD (Recurring Outflow) | **$0 / Local Subscription (Saves Foreign Currency)** |
| **Core Architecture** | Legacy/Monolithic (Resource Heavy) | **Modern Symfony + Go (Ultra-Lightweight)** |
| **Web Server** | Apache/Nginx (Standard) | **OpenLiteSpeed (3x Faster Performance)** |
| **Local Payments** | Requires costly 3rd party plugins | **Native bKash, Nagad, Upay & SSLCommerz** |
| **Global Payments** | Standard (PayPal/Stripe) | **Native PayPal & Stripe Integration** |
| **ISP & Networking** | Not Supported (Requires Splynx/Radius) | **Built-in Radius Engine & MikroTik API** |
| **GIS Capability** | None | **Integrated Google Maps for Asset Tracking** |
| **Deployment** | Manual/Complex Installation | **One-Command Cloud-init Installation** |
| **Data Sovereignty** | Data managed by foreign entities | **100% Sovereign Data Control by CAT Bangladesh** |

---

##🤝 Contribution & SSponsorship
We invite developers (Symfony/Golang/DevOps) and sponsors to join us in building this national technology layer. This project aims to put Bangladesh on the global map of cloud infrastructure providers.
​Lead: Ashrafuzzaman Khan (Founder & CEO)
​Organization: Cyber Adversary Taskforce (CAT) Bangladesh
​Location: Jessore, Bangladesh.
​Website: catbangladesh.com
​© 2026 CAT Bangladesh. All Rights Reserved.
