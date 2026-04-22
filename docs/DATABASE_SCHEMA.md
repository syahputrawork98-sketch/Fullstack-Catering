# Database Schema: Fullstack Catering (SvelteKit + Drizzle)

Rancangan database PostgreSQL menggunakan Drizzle ORM untuk menjamin integritas data operasional katering instansi.

## 📊 Entity Relationship Diagram (ERD) - Conceptual

### 1. Users (Autentikasi & RBAC)
Menyimpan data akun untuk seluruh modul (Admin, CS, User).
- `id`: UUID (PK)
- `name`: String
- `phone`: String (Unique, ID Login)
- `password`: String (Hashed with Argon2)
- `role`: Enum (`ADMIN`, `CUSTOMER_SERVICE`, `USER`)
- `category`: Enum (`PUBLIK`, `INSTANSI_BISNIS`, `INSTANSI_PEGAWAI`)
- `instansi_name`: String (Nama instansi/bisnis jika kategori bukan Publik)
- `status`: Enum (`PENDING`, `ACTIVE`)
    - *Logika Bisnis*: `INSTANSI_BISNIS` default ke `PENDING` (butuh verifikasi admin). Kategori lain default ke `ACTIVE`.
- `image`: String (URL Profile Picture)
- `created_at`: Timestamp

### 2. Menu Types (Jenis Menu)
Tabel dinamis untuk pengelompokan besar menu (e.g., Daily, Paket, Buffet).
- `id`: UUID (PK)
- `name`: String (e.g., "Menu Daily")
- `slug`: String (Unique)
- `created_at`: Timestamp

### 3. Menu Categories (Kategori Produk)
Tabel dinamis untuk jenis hidangan (e.g., Nasi Kotak, Bento, Snack).
- `id`: UUID (PK)
- `name`: String (e.g., "Nasi Kotak")
- `slug`: String (Unique)
- `created_at`: Timestamp

### 4. Menus (Master Produk)
Setiap menu wajib terikat pada satu Tipe dan satu Kategori.
- `id`: UUID (PK)
- `name`: String
- `description`: Text
- `base_price`: Decimal (Precision 12, Scale 2)
- `image`: String (URL/Path Foto)
- `type_id`: UUID (FK -> MenuTypes.id)
- `category_id`: UUID (FK -> MenuCategories.id)
- `created_by`: UUID (FK -> Users.id)
- `created_at`: Timestamp

### 5. DailySchedules (Jadwal Katalog Harian)
- `id`: Serial (PK)
- `menu_id`: UUID (FK -> Menus.id)
- `available_date`: Date (YYYY-MM-DD)
- `supply`: Integer (Total porsi awal yang disediakan)
- `current_stock`: Integer (Sisa porsi real-time)
- `created_at`: Timestamp

### 6. Orders (Transaksi Utama)
- `id`: UUID (PK)
- `user_id`: UUID (FK -> Users.id)
- `status`: Enum (`PENDING`, `PAID`, `CANCELLED`, `SHIPPED`, `COMPLETED`)
- `total_base_price`: Decimal **(PLANNED)**
- `total_tax`: Decimal **(PLANNED)**
- `grand_total`: Decimal
- `delivery_date`: Date (Tanggal pengiriman pesanan)
- `payment_method`: Enum (`CASH`, `TRANSFER`) **(PLANNED)**
- `payment_status`: Enum (`UNPAID`, `PAID`) **(PLANNED - Integrated in status as PAID)**
- `payment_proof`: String (URL/Base64 Bukti Bayar - Optimized: 800px width, 90% quality)
- `created_at`: Timestamp

### 7. OrderItems (Snapshot Pesanan)
- `id`: Serial (PK)
- `order_id`: UUID (FK -> Orders.id)
- `menu_id`: UUID (FK -> Menus.id)
- `quantity`: Integer
- `price_snapshot`: Decimal (Snapshot harga saat dipesan)

### 8. Expenses (Pengeluaran Operasional)
- `id`: UUID (PK)
- `amount`: Decimal
- `description`: Text
- `category`: Text (Default: 'BELANJA')
- `expense_date`: Date
- `created_at`: Timestamp

### 9. Audit Logs (Log Aktivitas)
- `id`: Serial (PK)
- `user_id`: UUID (FK -> Users.id)
- `action`: String (e.g., 'UPDATE_STOCK')
- `entity_type`: String (e.g., 'ORDER')
- `entity_id`: String
- `details`: Text (JSON String)
- `created_at`: Timestamp

### 10. Auth.js Tables (Sistem Sesi)
- `accounts`: Link provider OAuth/Kredensial ke User.
- `sessions`: Token sesi aktif.
- `verification_tokens`: Token untuk verifikasi email/password.

---

## 🔒 Integritas Data (Constraints)
1. **Stock Check**: `current_stock` wajib memiliki constraint `>= 0` di level database dan aplikasi.
2. **Atomic Update**: Pengurangan stok saat checkout dilakukan dalam **Database Transaction**.
3. **Price Snapshot**: Menjamin akurasi laporan keuangan histori meskipun harga Master Menu berubah.
4. **Cascade Delete**: Relasi OrderItems dan DailySchedules menggunakan `ON DELETE CASCADE`.

---
*Created by: Chief Architecture Governor*  
*Refined for Synchronization: 2026-04-22 (Antigravity Update)*
