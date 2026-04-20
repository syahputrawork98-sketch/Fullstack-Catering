# ⚙️ KANBAN BACKEND - Module [CUSTOMER SERVICE]

Fokus: Agregasi data operasional, mutasi status pesanan, dan manajemen master menu.

---

## 🏗️ Data Logic Atomic Status Board

| Phase | Logic / API Detail | Atom Detail | Status |
| :--- | :--- | :--- | :--- |
| **04** | **Status Mutation** | DB UPDATE for Order Status | [x] DONE |
| **07** | **Stats Aggregation** | SQL filter + count for dashboard | [x] DONE |
| **07** | **Master Menu CRUD** | INSERT into menus + image placeholder | [x] DONE |
| **07** | **Client Creation** | Manual INSERT for INSTANSI accounts | [x] DONE |

---

## 📝 Micro-Atomic Technical Checklist (Learning Resource)

### Phase 04: Order Operations (Done)
- [x] **Status Update API**
    - [x] **File**: `src/routes/cs/orders/+page.server.ts`.
    - [x] **Logic**: Handle `updateStatus` action with RBAC check.
- [x] **Relational Order Fetch**
    - [x] **Query**: Use `db.query.orders.findMany` with `with: { user: true, orderItems: { with: { menu: true } } }`.

### Phase 07: Dashboards & Stats (Done)
- [x] **Operational Stats Loader**
    - [x] **File**: `src/routes/cs/+page.server.ts`.
    - [x] **Logic**: Use `sql` helper for complex counts (`filter (where date(created_at) = current_date)`).
    - [x] **Logic**: Aggregate "Low Stock" from `daily_schedules` for current date.
- [x] **Client Management Logic**
    - [x] **File**: `src/routes/cs/+page.server.ts` (or Admin page).
    - [x] **B2B Path**: Implement `createInstansi` action with Argon2 password hashing.
    - [x] **Status**: Default new Instansi accounts to `ACTIVE`.

### Phase 07.5: Server Integrity (Done)
- [x] **RBAC Logic Hardening**
    - [x] Ensure `rbacHandle` covers the new `/cs` and `/admin` routes with strict type checks.
- [x] **B2B Payload Validation**
    - [x] Tighten input validation for manual Instansi creation.

### Phase 07.6: UI Audit Enablement (In Progress)
- [ ] **Auth Bypass for Audit**
    - [ ] Create a dev-flag to temporarily disable `authHandle` and `rbacHandle` for UI walkthroughs.

### Phase 08: Puzzle Masa Depan (Planned)
- [ ] **Real-time Push Notifications**
    - [ ] Simple long-polling or SSE for new order alerts.
- [ ] **Stock Prediction Logic**
    - [ ] Suggesing daily limits based on historical averages.
