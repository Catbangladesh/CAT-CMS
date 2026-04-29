# Billing & Automation Logic 💰

This document defines the core financial workflow and automation engine for **CAT CMS**, designed to meet the standards of industry leaders like WHMCS and Blesta.

## 1. Product & Service Lifecycle
- **Flexible Billing Cycles:** Support for Monthly, Quarterly, Semi-Annually, and Annually.
- **Pro-Rata Billing:** Ability to adjust pricing based on the date of purchase to align with a specific billing date (e.g., the 1st of every month).
- **Auto-Provisioning:** Upon successful payment verification via API, the system must automatically trigger server-side scripts to create the hosting account or ISP profile.

## 2. Invoicing & Payment
- **Invoice Generation:** Automated generation of PDF invoices X days before the due date.
- **Credit System:** Clients can add funds to their "Digital Wallet," which the system will automatically apply to unpaid invoices.
- **Tax Rules:** Regional tax/VAT configuration based on the client's country or state.
- **Multi-Currency:** Support for BDT, USD, and other currencies with real-time conversion options.

## 3. Automation & Suspension (The "Killer" Feature)
- **Grace Period:** Configurable days after the due date before service impact.
- **Auto-Suspension:** If an invoice remains unpaid after the grace period, the system must automatically:
    - Disable Nginx/Apache configuration for Hosting.
    - Disable the Radius account/PPPoE session for ISP users.
- **Late Fees:** Automatically add a fixed or percentage-based penalty fee to overdue invoices.
- **Termination:** Auto-deletion of data after X days of suspension (requires admin-defined threshold).

## 4. Promo & Affiliate Engine
- **Coupon Codes:** Support for one-time or recurring discounts (Percentage or Fixed amount).
- **Affiliate System:** Tracking referrals via cookies and awarding commissions to referrers upon successful client payments.

## 5. Gateway Integration
- **Local Gateways (Bangladesh):** Native integration for bKash, Nagad, Rocket, and SSLCommerz.
- **International Gateways:** Integration for Stripe, PayPal, and Authorize.net.

---
*This logic ensures that CAT CMS acts as a complete ERP, reducing manual intervention to zero.*
