# Database Schema Design (ERP & Control Panel) 🗄️

This document outlines the core database structure required to support a WHMCS/Blesta-grade billing system combined with a Linux Control Panel.

## 1. User & Authentication
- **users:** `id`, `name`, `email`, `password`, `role` (admin, client, support), `status` (active, suspended).
- **client_profiles:** `user_id`, `company_name`, `address`, `phone`, `currency`, `balance` (for credit system).

## 2. Inventory & Services
- **products:** `id`, `name`, `type` (shared_hosting, vps, isp_plan, domain), `description`.
- **pricing:** `product_id`, `billing_cycle` (monthly, yearly), `amount`, `setup_fee`.
- **user_services:** `id`, `user_id`, `product_id`, `server_id`, `domain_name`, `next_due_date`, `status` (pending, active, suspended, terminated).

## 3. Server Management
- **servers:** `id`, `name`, `ip_address`, `hostname`, `api_token`, `provider`, `max_accounts`, `status`.
- **server_groups:** For load balancing or specific location-based provisioning.

## 4. Billing & Transactions
- **invoices:** `id`, `user_id`, `total`, `subtotal`, `tax`, `status` (paid, unpaid, cancelled, overdue), `due_date`, `date_paid`.
- **invoice_items:** `invoice_id`, `description`, `amount`, `user_service_id`.
- **transactions:** `id`, `invoice_id`, `gateway` (bkash, stripe, paypal), `transaction_id`, `amount`, `date`.

## 5. ISP & Radius (Specific for CAT CMS)
- **radius_profiles:** Linked to `user_services` for managing PPPoE/Hotspot speed limits.
- **bandwidth_usage:** `service_id`, `download`, `upload`, `timestamp` (for graphing).

## 6. Support & CRM
- **tickets:** `id`, `user_id`, `subject`, `department`, `priority`, `status` (open, answered, closed).
- **ticket_replies:** `ticket_id`, `user_id`, `message`, `attachments`.

---

## Entity Relationship (ER) Summary:
1. A **User** can have multiple **Invoices** and **Services**.
2. A **Service** is linked to a **Product** and a **Server**.
3. **Invoices** generate **Transactions** upon payment.
4. **Transactions** trigger the **Automation Engine** to activate **Services** on the **Server**.
