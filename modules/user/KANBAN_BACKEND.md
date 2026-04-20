# ⚙️ KANBAN BACKEND - Module [USER]

Fokus: Integritas data, keamanan autentikasi, dan logika transaksi database.

---

## 🛠️ Logic & Database Status Board

| Task | Status | Priority | Notes |
| :--- | :--- | :--- | :--- |
| **Auth Logic** | [x] DONE | High | Argon2id + JWT Strategy. |
| **User CRUD** | [/] IN-PROG | High | Create/Read Done. Update Planned. |
| **Order Engine** | [x] DONE | High | Atomic transactions for Orders. |
| **Relational Queries** | [x] DONE | High | Drizzle relational with Items & Menus. |
| **Stock decrement** | [ ] PLANNED | High | Inventory sync logic. |
| **PDF Logic** | [x] DONE | Medium | Client-side jsPDF utility. |

---

## 📝 Atomic Task Checklist

### 1. Security & Identity
- [x] **Registration Logic**: Password hashing and unique constraint handling.
- [x] **Session Guard**: Auth.js integration with SvelteKit locals.
- [ ] **Profile Update**: Backend mutation for user data changes.

### 2. Transactional Core
- [x] **Relational Loaders**: Fetching orders with nested items and menus.
- [x] **Price Snapshots**: Ensuring historical prices are saved on order.
- [ ] **Atomic Inventory**: Safe stock reduction using PG transactions.

---
*Back to [Master Kanban](../../PROGRESS_KANBAN_MASTER.md)*
