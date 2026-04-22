# ⚙️ KANBAN BACKEND - Module [CUSTOMER SERVICE]

Fokus: Agregasi data operasional, mutasi status pesanan, dan manajemen master menu.

---

## 🏗️ Data Logic Atomic Status Board

| Phase | Logic / API Detail | Atom Detail | Status |
| :--- | :--- | :--- | :--- |
| **05** | **Status Mutation** | DB UPDATE for Order Status | [x] DONE |
| **05** | **Stats Aggregation** | SQL filter + count for dashboard | [x] DONE |
| **03** | **Master Menu CRUD** | INSERT into menus + image placeholder | [x] DONE |
| **05** | **Client Creation** | Manual INSERT for INSTANSI accounts | [x] DONE |

---

## 📝 Micro-Atomic Technical Checklist (Learning Resource)

### Phase 03: Core Menu Master (Done)
- [x] **Master Menu CRUD**
    - [x] INSERT into menus table.
- [x] **Stock & Catalog Management**
    - [x] Implemented `updateStock` action in `/cs/stock`.

### Phase 05: Operational Dashboards (Done)
- [x] **Status Update API**
    - [x] **File**: `src/routes/cs/orders/+page.server.ts`.
- [x] **Operational Stats Loader**
    - [x] **File**: `src/routes/cs/+page.server.ts`.
- [x] **Client Management Logic**
    - [x] Implemented `createClient` and `toggleStatus` in `/cs/clients`.

### Phase 08: Integrity & Security (Done)
- [x] **RBAC Logic Hardening**
    - [x] Ensure `rbacHandle` covers the new `/cs` and `/admin` routes.
- [x] **Auth Bypass for Audit**
    - [x] Fixed `mock-audit-id` to valid UUID in `hooks.server.ts`.

### Phase 11: Puzzle Masa Depan (Planned)
- [ ] **Real-time Push Notifications**
    - [ ] Simple long-polling or SSE for new order alerts.
- [ ] **Stock Prediction Logic**
    - [ ] Suggesing daily limits based on historical averages.
