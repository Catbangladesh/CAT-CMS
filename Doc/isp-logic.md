# ISP Management Logic 🌐

This document defines how CAT CMS handles ISP-specific operations and bandwidth control.

### 1. User Authentication (Radius)
- The system must integrate with **FreeRadius** to manage PPPoE and Hotspot users.
- Users created in CAT CMS should automatically sync with the Radius database.

### 2. Bandwidth & Speed Limitation
- **Profiles:** Admin can create profiles (e.g., 5Mbps, 10Mbps, 20Mbps).
- **Queues:** Integration with MikroTik API or Linux Traffic Control (tc) to enforce speed limits.
- **FUP Logic:** Fair Usage Policy to reduce speed after a certain data limit is reached.

### 3. Real-time Monitoring
- Monitoring active sessions (Who is online/offline).
- Graphing bandwidth usage per user (using RRDtool or Prometheus).
