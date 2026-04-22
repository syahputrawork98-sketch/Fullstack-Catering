# ⚙️ KANBAN BACKEND - Module [ADMIN]

Fokus: Keamanan tingkat tinggi, agregasi finansial, dan otoritas sistem pusat.

---

## 🏗️ Data Logic Atomic Status Board

| Phase | Logic / API Detail | Atom Detail | Status |
| :--- | :--- | :--- | :--- |
| **10** | **Role Hierarchy** | ADMIN has access to all routes | [x] DONE |
| **05** | **System Stats API** | Global SQL aggregation across tables | [x] DONE |
| **08** | **Audit Enablement** | Dev-flag Auth Bypass + Mock Sessions | [x] DONE |
| **06** | **Financial Engine** | Revenue (Orders) vs Expenses (Belanja) | [x] DONE |
| **06** | **Route Authority** | Users, Reports, & Settings Loaders | [x] DONE |

---

## 📝 Micro-Atomic Technical Checklist (Learning Resource)

### Phase 05: Operations & Stats (Done)
- [x] **Global Statistics Loader**
    - [x] **File**: `src/routes/admin/+page.server.ts`.
    - [x] **Aggregation**: Multi-table count for total users, instansi count, and total revenue.
- [x] **Manual Instansi Creator**
    - [x] Receive `instansiName`, `phone`, and `password`.

### Phase 06: Financial Mastery (Done)
- [x] **Revenue & Expense Aggregation**
    - [x] **Logic**: Aggregate `COALESCE(sum(grandTotal), 0)` and `COALESCE(sum(amount), 0)`.
- [x] **Sub-route Loaders**
    - [x] **Users**: Management loader.
    - [x] **Reports**: Advanced financial aggregation.

### Phase 07: System Audit (Done)
- [x] **Data Backup & Export**
    - [x] **File**: `src/routes/admin/api/export/+server.ts`.
- [x] **Audit Trail Viewer**
    - [x] **File**: `src/routes/admin/audit/+page.server.ts`.

### Phase 08 & 10: Integrity & Security (Done)
- [x] **Context Injection for Audit**
    - [x] Fixed `mock-audit-id` to valid UUID in `hooks.server.ts`.
- [x] **Policy Augmentation**
    - [x] Update `Session` types and tighten `rbacHandle`.

### Phase 11: Puzzle Masa Depan (Planned)
- [ ] **Advanced Data Backup**
    - [ ] Automating scheduled database dumps.
- [ ] **Visual Audit Analytics**
    - [ ] Charts for audit activity trends.
