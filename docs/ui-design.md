# UI/UX Design Specifications 🎨

## 1. Design Base
CAT CMS will be built using **AdminLTE 4 (Bootstrap 5)**. We aim for a unique, clean, and "SaaS-style" professional look, moving away from cluttered legacy panels.

## 2. Visual Direction
- **Primary Theme:** Professional Dark Mode (default) with a high-contrast Light Mode toggle.
- **Accent Colors:** Primary Color `#2A5CFF` (Electric Blue) to represent technology and speed.
- **Typography:** Inter or Roboto for maximum readability on server logs and billing data.

## 3. Dashboard Layout (Unique Features)
- **Modular Widgets:** The Admin dashboard should feature draggable widgets for:
    - Live Server Health (CPU/RAM Graph).
    - Real-time ISP Bandwidth Monitor.
    - Today's Income & Pending Invoices.
- **Unified Search:** A "Command Palette" (Ctrl+K) style search to quickly find Clients, Domains, or IP Addresses.

## 4. Key UI Components
### A. The "All-in-One" Sidebar
Instead of separating Billing and Hosting, the sidebar should be unified:
- **Operations:** Site Manager, DB Manager, SSL, File Manager.
- **Clients:** Client List, Support Tickets, KYC.
- **Financials:** Invoices, Gateways, Revenue Reports.
- **ISP:** Radius Profiles, NAS/MikroTik Sync, Bandwidth Logs.

### B. Client Portal (UX Focus)
The Client UI must be simplified for non-technical users:
- **One-Click Actions:** "Renew Service", "Upgrade Plan", and "Login to Webmail" should be visible on the landing page.
- **Responsive Design:** Full functionality on mobile devices to allow ISP users to pay bills on the go.

## 5. Frontend Stack
- **Framework:** Laravel Livewire (for real-time UI updates without page refreshes).
- **CSS:** Tailwind CSS for custom components on top of Bootstrap 5 (AdminLTE).
- **Icons:** FontAwesome 6 & Lucide Icons.

---
*The goal is to create a UI that feels like a premium SaaS product, not a complicated 2010-era control panel.*
