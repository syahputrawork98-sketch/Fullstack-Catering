# ⚙️ KANBAN BACKEND - Module [CUSTOMER SERVICE]

Fokus: Validasi status, otorisasi CS, dan sinkronisasi pesanan.

---

## 🛠️ Logic & Database Status Board

| Task | Status | Priority | Notes |
| :--- | :--- | :--- | :--- |
| **Status Mutation** | [x] DONE | High | Server-side status updates (Auth-guarded). |
| **CS Authorization** | [x] DONE | High | RBAC check for CS-only routes. |
| **All Orders Loader** | [x] DONE | High | Efficient retrieval of cross-user orders. |
| **Stats calculation** | [x] DONE | Medium | SQL aggregations for dashboard count cards. |

---

## 📝 Atomic Task Checklist

### 1. Control Logic
- [x] **RBAC Hook**: Ensure only users with `CUSTOMER_SERVICE` role can access the portal.
- [x] **Secure Update**: Form actions to mutate order status with validation.

### 2. Operational Data
- [x] **Query Engine**: Fetching all orders with customer details.
- [x] **Dash Stats**: Real-time counting of pending vs today's orders.

---
*Back to [Master Kanban](../../PROGRESS_KANBAN_MASTER.md)*
