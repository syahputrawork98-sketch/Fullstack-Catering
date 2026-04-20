# ⚙️ KANBAN BACKEND - Module [USER / CUSTOMER]

Fokus: Integritas data transaksi, keamanan RBAC, dan sinkronisasi stok atomik.

---

## 🏗️ Data Logic Atomic Status Board

| Phase | Logic / API Detail | Atom Detail | Status |
| :--- | :--- | :--- | :--- |
| **02** | **Argon2 Auth** | Secure Password Hashing | [x] DONE |
| **03** | **RBAC Guard** | Server-side Hooks Protection | [x] DONE |
| **04** | **Order Entry** | Drizzle INSERT into Orders | [x] DONE |
| **05** | **Date Resolver** | Fetching menus by availableDate | [x] DONE |
| **06** | **Atomic Stock Sync** | Stock subtraction in transaction | [x] DONE |
| **06** | **Delivery Date Tracking** | Column assignment in Orders | [x] DONE |

---

## 📝 Micro-Atomic Technical Checklist (Learning Resource)

### Phase 02 & 03: Security & Auth (Done)
- [x] **Secure Registration Handler**
    - [x] **File**: `src/routes/register/+page.server.ts`.
    - [x] **Logic**: Implement `argon2.hash(password)` for storage.
    - [x] **Logic**: Default user category to `PUBLIK` and status to `ACTIVE`.
- [x] **RBAC Protected Hooks**
    - [x] **File**: `src/hooks.server.ts`.
    - [x] **Logic**: Use `sequence(authHandle, rbacHandle)` to lock `/dashboard`.

### Phase 05: Core Menu Logic (Done)
- [x] **Date-Aware Catalog Loader**
    - [x] **File**: `src/routes/dashboard/menu/+page.server.ts`.
    - [x] **Query**: Use `db.query.dailySchedules.findMany` with `where: eq(availableDate, selectedDate)`.
    - [x] **Metadata**: Generate 7-day metadata for the frontend scroller using `new Date()`.

### Phase 06: Atomic Ordering (Done)
- [x] **Transaction-Based Checkout**
    - [x] **File**: `src/routes/dashboard/checkout/+page.server.ts`.
    - [x] **Atomicity**: Implement `db.transaction(async (tx) => { ... })`.
    - [x] **Validation**: Check `currentStock >= quantity` before proceeding.
    - [x] **Logic**: Subtract stock using `sql`${dailySchedules.currentStock} - ${quantity}``.
    - [x] **Integration**: Store `deliveryDate` (selected in catalog) into the `orders` record.

### Phase 07.5: System Integrity (Done)
- [x] **Global Type Augmentation**
    - [x] Declare `Session` and `User` modules in `app.d.ts`.
    - [x] Explicitly type `role` and `status` to fix layout errors.
- [x] **Auth.js Logic Polish**
    - [x] Ensure `jwt` and `session` callbacks handle type-casted roles safely.

### Phase 07.6: UI Creative Design Audit (In Progress)
- [ ] **User Portal Aesthetic Audit**
    - [ ] Refine date scroller visuals and layout consistency.
    - [ ] Audit Menu Cards for desktop larger screens.

### Phase 08: Puzzle Masa Depan (Planned)
- [ ] **Point Ledger Logic**
    - [ ] Auto-calculate and insert points based on `grandTotal`.
- [ ] **Cancellation Policy Engine**
    - [ ] Logic to allow/block cancellation based on `deliveryDate` proximity.
