# Module [CUSTOMER SERVICE (CS)] - Implementation Checklist

## 1. Dashboard CS (`/cs`)
- [ ] **A. Ringkasan Statistik (Daily Summary)**
    - [ ] **Frontend**: Kartu indikator "Total Porsi Terpesan" hari ini.
    - [ ] **Frontend**: Kartu indikator "Sisa Stok" (Visual progress bar).
    - [ ] **Frontend**: Kartu indikator "Pesanan Belum Diverifikasi".
    - [ ] **Backend**: Query `COUNT` pesanan aktif per tanggal hari ini.
    - [ ] **Backend**: Logic pengurangan `Total Supply - Total Terpesan`.
    - [ ] **Backend**: Real-time update data (SvelteKit invalidate/streaming).
- [ ] **B. Notifikasi Pesanan Khusus**
    - [ ] **Frontend**: List "Urgent Requests" dari alur WhatsApp.
    - [ ] **Backend**: Penarikan data pesanan dengan flag `SPECIAL_ORDER`.

## 2. Daily Scheduler (`/cs/scheduler`)
- [ ] **A. Form Input Menu Harian**
    - [ ] **Frontend**: Komponen Image Picker (Foto Menu).
    - [ ] **Frontend**: Input Field Nama, Harga, dan Limit Stok.
    - [ ] **Frontend**: Field "Keterangan Tambahan CS".
    - [ ] **Backend**: Script Image Compression & Conversion (WebP).
    - [ ] **Backend**: Proses `UPSERT` data ke tabel DailySchedules.

## 3. Order Monitor (`/cs/orders`)
- [ ] **A. Live Order Table**
    - [ ] **Frontend**: Tabel interaktif dengan filter Status (Pending/Done).
    - [ ] **Frontend**: Komponen "Badge Status" (Warna-warni sesuai progres).
    - [ ] **Backend**: Query join `Orders` + `Users` + `OrderItems`.
- [ ] **B. Cetak Rekap Dapur**
    - [ ] **Frontend**: Tombol "Print Rekap" (Print-friendly CSS).
    - [ ] **Backend**: Aggregasi total menu (Contoh: "Total Nasi Ayam: 50 kotak").

## 4. Payment & Management (`/cs/payments`)
- [ ] **A. Verifikasi Pembayaran**
    - [ ] **Frontend**: Galeri Bukti Transfer (Zoom-in modal).
    - [ ] **Frontend**: Tombol Konfirmasi Pembayaran.
    - [ ] **Backend**: Logic update `payment_status` dan `order_status`.
- [ ] **B. Input Akun Instansi Manual**
    - [ ] **Frontend**: Form Pembuatan User (Username, Pass, Dept).
    - [ ] **Backend**: Logic registrasi user oleh CS (Bypass pending status).
