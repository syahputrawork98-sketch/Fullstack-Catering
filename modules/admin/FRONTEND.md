# Module [ADMIN / SUPER ADMIN] - Implementation Checklist

## 1. Admin Control Hub (`/admin`)
- [/] **A. Portal & Kerangka Dashboard**
    - [x] **Frontend**: Layout Dasar Admin Control Center (Dark Theme).
    - [x] **Frontend**: Sidebar & Navigation Staff Admin.
    - [x] **Backend**: Proteksi Rute Admin (RBAC Middleware).
- [ ] **B. Laporan Mingguan & Bulanan**
    - [ ] **Frontend**: Grafik garis tren mingguan/bulanan.
    - [ ] **Backend**: Query agregasi `SUM` per `week` / `month`.
- [ ] **C. Analisis Efisiensi (Terjual vs Sisa)**
    - [ ] **Frontend**: Pie chart "Porsi Terjual vs Sisa".
    - [ ] **Backend**: Perhitungan selisih `Stok Awal - Stok Dipesan` per periode.

## 2. User Management (`/admin/users`)
- [ ] **A. Approval Pendaftaran Instansi**
    - [ ] **Frontend**: List user dengan status `PENDING`.
    - [ ] **Frontend**: Tombol Approve (Satu klik) & Reject (dengan alasan).
    - [ ] **Backend**: Update status `is_active` dan notifikasi email (opsional).
- [ ] **B. Pengaturan Staff CS**
    - [ ] **Frontend**: Form input data CS baru.
    - [ ] **Backend**: Set role `CUSTOMER_SERVICE` di database.

## 3. System Config (`/admin/settings`)
- [ ] **A. Identitas & Pajak**
    - [ ] **Frontend**: Form upload Logo instansi katering.
    - [ ] **Frontend**: Input persentase PPN (Vat).
    - [ ] **Backend**: Penyimpanan JSON Config di database.
- [ ] **B. Email System**
    - [ ] **Frontend**: Pengaturan SMTP/Email (`admin@wikatering.com`).
    - [ ] **Backend**: Integrasi library email sender.

## 4. Audit Log (`/admin/logs`)
- [ ] **A. Sistem Pelacakan Aktivitas**
    - [ ] **Frontend**: Tabel histori aktivitas yang bisa difilter.
    - [ ] **Backend**: Middleware Audit Log (Track: Siapa mengubah Apa pada jam Berapa).
