# Module [CUSTOMER SERVICE] - Backend Atomic Tasks

Fokus pada manajemen menu harian, pengolahan gambar, dan verifikasi operasional.

## 1. Master Menu (CRUD)
- [ ] **Data Management**
    - [ ] **Create**: Simpan menu baru (Nama, Deskripsi, Harga Dasar).
    - [ ] **Read**: Fetching daftar semua menu master.
    - [ ] **Update**: Edit informasi menu master.
    - [ ] **Delete**: Hapus menu master (dengan kaitan relasi).

## 2. Daily Menu Scheduler (CRUD)
- [ ] **Scheduling Logic**
    - [ ] **Create**: Daftarkan menu ke tanggal tertentu.
    - [ ] **Read**: Ambil jadwal menu untuk tanggal tertentu.
    - [ ] **Update**: Ubah stok porsi atau ganti menu pada tanggal yang sudah ada.
    - [ ] **Delete**: Batalkan menu pada tanggal tertentu.

## 3. Image Processing Service
- [ ] **Automated Compression Pipeline**
    - [ ] Logic Resize & Convert harian ke format WebP.

## 4. Order & Payment Monitor
- [ ] **Operational Queries**
    - [ ] Aggregasi pesanan harian: "Siapa pesan Apa".
    - [ ] **Update**: Endpoint verifikasi `payment_status` dan `order_status`.

## 5. Forced Account Creation
- [ ] **CS Assisted Register**
    - [ ] **Create**: Logic pembuatan user oleh staff CS (Direct Active).
