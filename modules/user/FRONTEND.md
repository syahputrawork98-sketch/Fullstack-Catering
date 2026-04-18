# Module [USER / CUSTOMER] - Implementation Checklist

## 1. Login & Registration
- [ ] **A. Proses Pendaftaran**
    - [ ] **Frontend**: Form input (Nama, No Telp, Pass).
    - [ ] **Frontend**: Dropdown pilihan "Instansi vs Umum".
    - [ ] **Backend**: Validasi duplikasi nomor telepon.
    - [ ] **Backend**: Password Hashing (Keamanan).
- [ ] **B. Proses Login**
    - [ ] **Frontend**: Form login & Feedback error.
    - [ ] **Backend**: JWT Session Management (NextAuth).

## 2. Dashboard Catalog (`/dashboard`)
- [ ] **A. Katalog Menu Harian**
    - [ ] **Frontend**: Skeleton loading (Tampilan saat data dimuat).
    - [ ] **Frontend**: Card Menu (Foto, Nama, Info Stok).
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
