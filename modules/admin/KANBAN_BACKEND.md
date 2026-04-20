# ⚙️ KANBAN BACKEND - Module [ADMIN]

Fokus: Keamanan tingkat tinggi, agregasi finansial, dan otoritas sistem pusat.

---

## 🏗️ Data Logic Atomic Status Board

| Phase | Logic / API Detail | Atom Detail | Status |
| :--- | :--- | :--- | :--- |
| **03** | **Role Hierarchy** | ADMIN has access to all routes | [x] DONE |
| **07** | **System Stats API** | Global SQL aggregation across tables | [x] DONE |
| **07.6** | **Audit Enablement** | Dev-flag Auth Bypass + Mock Sessions | [x] DONE |
| **08** | **Financial Engine** | Revenue (Orders) vs Expenses (Belanja) | [x] DONE |
| **08.1** | **Route Authority** | Users, Reports, & Settings Loaders | [x] DONE |

---

## 📝 Micro-Atomic Technical Checklist (Learning Resource)

### Phase 03 & 07: Control & Stats (Done)
- [x] **Global Statistics Loader**
    - [x] **File**: `src/routes/admin/+page.server.ts`.
    - [x] **Aggregation**: Multi-table count for total users, instansi count, and total revenue.
    - [x] **Security**: Rigid check: `if (session.user.role !== 'ADMIN') throw error(403)`.
- [x] **Master User Audit**
    - [x] **Query**: Get latest 5 registrations with `orderBy: [desc(users.id)]`.

### Phase 07: Account Authority (Done)
- [x] **Manual Instansi Creator**
    - [x] **File**: `src/routes/admin/+page.server.ts`.
    - [x] **Logic**: Receive `instansiName`, `phone`, and `password`.
    - [x] **Security**: Use `argon2` to hash before storage.
    - [x] **Integrity**: Set status to `ACTIVE` by default for staff-created accounts.

### Phase 07.5: Otoritas & Policy (Done)
- [x] **Policy Augmentation**
    - [x] Update `Session` type declarations to include `Admin` specific fields.
    - [x] Tighten `rbacHandle` for financial data protection.

### Phase 07.6: UI Audit Enablement (Done)
- [x] **Context Injection for Audit**
    - [x] **File**: `src/hooks.server.ts`.
    - [x] **Logic**: Implement `AUDIT_MODE` with mock user session injection to prevent layout crashes.
- [x] **Expense Logger API**
    - [x] **Action**: `logExpense` handler to insert shopping data into `expenses` table.

### Phase 08: Financial Mastery (Done)
- [x] **Revenue & Expense Aggregation**
    - [x] **Logic**: Aggregate `COALESCE(sum(grandTotal), 0)` and `COALESCE(sum(amount), 0)`.
    - [x] **Security**: Use `inArray` to only count `PAID`, `SHIPPED`, or `COMPLETED` orders.
- [x] **Sub-route Loaders (Phase 08.1)**
    - [x] **Users**: Loader to fetch 100% of the user base for management.
    - [x] **Reports**: Advanced financial aggregation for the analytics hub.
    - [x] **Settings**: Static config loader for V1 metadata.

### Phase 09: Puzzle Masa Depan (Planned)
- [ ] **Data Backup & Restore**
    - [ ] Logic to export/import the entire postgres database state.
- [ ] **Audit Trail Viewer**
    - [ ] View critical status changes and by whom they were edited.
