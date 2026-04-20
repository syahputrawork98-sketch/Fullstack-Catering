# Module [USER / CUSTOMER] - Implementation Checklist

## 1. Login & Registration
- [x] **A. Proses Pendaftaran**
    - [x] **Frontend**: Form input (Nama, No Telp, Pass) dengan Svelte 5 Runes.
    - [x] **Frontend**: Dropdown pilihan "Instansi vs Umum".
    - [x] **Backend**: Validasi duplikasi nomor telepon (Database unique constraint).
    - [x] **Backend**: Password Hashing (Argon2id).
- [x] **B. Proses Login**
    - [x] **Frontend**: Form login & Feedback error.
    - [x] **Backend**: JWT Session Management (Auth.js Strategy: JWT).

## 2. Dashboard Catalog (`/dashboard`)
- [x] **A. Katalog Menu Harian**
    - [x] **Frontend**: UI Framework & Grid System (High-Aesthetic).
    - [x] **Frontend**: Sidebar Navigation (Orders, Menu, Profile) - *Ready*.
    - [x] **Frontend**: Premium Card Menu (Foto, Nama, Info Stok).
    - [ ] **Backend**: Query menu `available_date = TODAY`.
- [ ] **B. Sistem Keranjang**
    - [ ] **Frontend**: Modal Preview Keranjang.
    - [ ] **Frontend**: Sinkronisasi LocalStorage (Data tidak hilang jika refresh).
    - [ ] **Backend**: Validasi stok sisa di server saat klik "Add to Cart".

## 3. Checkout & Payment (`/dashboard/cart`)
- [ ] **A. Finalisasi Checkout**
    - [ ] **Frontend**: Rincian Biaya (Total Harga Pokok + PPN).
    - [ ] **Frontend**: Tombol "Pesan Sekarang".
    - [ ] **Backend**: Store `price_snapshot` dan `tax_snapshot`.
    - [ ] **Backend**: Update stok otomatis (PostgreSQL Transaction).

## 4. Tracking & History (`/dashboard/orders`)
- [ ] **A. Monitoring Status Aktif**
    - [ ] **Frontend**: Visual Stepper (Order -> Diproses -> Kirim -> Selesai).
    - [ ] **Frontend**: Tombol "Download Bon PDF" (Thermal format).
- [ ] **B. Riwayat Belanja (History)**
    - [ ] **Frontend**: List pesanan masa lalu dengan filter bulan.
    - [ ] **Backend**: Query riwayat per `user_id`.
