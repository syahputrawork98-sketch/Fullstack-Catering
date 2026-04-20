# Module [USER] - Backend Atomic Tasks

Fokus pada integritas transaksi, pendaftaran, dan pengelolaan riwayat pesanan.

## 1. Authentication & Profile (CRUD)
- [ ] **Account Management**
    - [x] **Create**: Logic registrasi user baru (Argon2 Hashing).
    - [x] **Read**: Ambil data profil user saat ini (via SvelteKit Session).
    - [ ] **Update**: Edit data mandiri (Nama, No Telp, Password).
- [x] **Auth Session**
    - [x] Integrasi Auth.js (JWT Strategy) & Adapter.

## 2. Catalog & Inventory System
- [x] **Daily Catalog Resolver**
    - [x] Query menu `available_date = TODAY`.
- [ ] **Stock Monitoring**
    - [ ] API penghitung sisa stok real-time.

## 3. Order & Payment Engine
- [x] **Checkout Process**
    - [x] Database Transaction: Create Order & OrderItems (Atomic).
    - [ ] Database Transaction: Decrement Stock (Atomic) - *Planned for Inventory Phase*.
- [x] **Snapshot Logic**
    - [x] Ambil snapshot harga menu saat transaksi (`price_snapshot`).

## 4. Document & History Service
- [ ] **PDF Generator**
    - [ ] Logic pembuatan PDF struk digital.
- [x] **History & Search**
    - [x] **Read**: Query riwayat transaksi per `user_id` (Drizzle Relational).
