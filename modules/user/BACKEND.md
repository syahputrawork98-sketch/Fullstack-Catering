# Module [USER] - Backend Atomic Tasks

Fokus pada integritas transaksi, pendaftaran, dan pengelolaan riwayat pesanan.

## 1. Authentication & Profile (CRUD)
- [ ] **Account Management**
    - [ ] **Create**: Logic registrasi user baru.
    - [ ] **Read**: Ambil data profil user saat ini.
    - [ ] **Update**: Edit data mandiri (Nama, No Telp, Password).
- [ ] **Auth Session**
    - [ ] Integrasi Auth.js / NextAuth (JWT Layer).

## 2. Catalog & Inventory System
- [ ] **Daily Catalog Resolver**
    - [ ] Query menu `available_date = TODAY`.
- [ ] **Stock Monitoring**
    - [ ] API penghitung sisa stok real-time.

## 3. Order & Payment Engine
- [ ] **Checkout Process**
    - [ ] Database Transaction: Create Order & OrderItems.
    - [ ] Database Transaction: Decrement Stock (Atomic).
- [ ] **Snapshot Logic**
    - [ ] Ambil snapshot harga menu saat transaksi.

## 4. Document & History Service
- [ ] **PDF Generator**
    - [ ] Logic pembuatan PDF struk digital.
- [ ] **History & Search**
    - [ ] **Read**: Query riwayat transaksi per `user_id`. (Termasuk filter tanggal).
