# Business Logic: Fullstack Catering (Internal Hub)

Aturan operasional dan pembagian tanggung jawab untuk sistem katering instansi.

## 👥 Modul & Tanggung Jawab (Roles)

### 1. Modul [PUBLIC] - Etalase Umum
- **Akses**: Terbuka untuk semua (tanpa login).
- **Konten**: Profil Instansi, panduan pemesanan, informasi kontak CS, dan FAQ.

### 2. Modul [USER / CUSTOMER] - Pemesanan Internal
- **Pendaftaran (Self-Register)**:
  - Form minimalis: **Nama**, **Nomor Telepon**, dan **Password**.
  - Pilihan Kategori: **Umum/Publik** (Default) atau **Instansi**.
  - **Catatan Validasi**: Pendaftaran dengan kategori "Instansi" akan berstatus **PENDING** dan membutuhkan verifikasi sdm/admin sebelum fitur instansi aktif.
- **Siklus Pemesanan**:
  - **Jam Buka**: Pemesanan dibuka mulai pukul **08:00 WIB**.
  - **Jam Tutup (Cut-off)**: Pemesanan ditutup pukul **13:00 WIB**.
  - **Pembatalan**: User dapat membatalkan pesanan maksimal pukul **11:30 WIB**. Pembatalan di atas jam tersebut harus melalui persetujuan manual CS/Admin (sebelum jam 12:00).
- **Fitur Utama**: Katalog harian, keranjang, checkout, Download Bon PDF, dan Riwayat Pesanan.

### 3. Modul [CUSTOMER SERVICE (CS)] - Operasional & Posting
- **Manajemen Menu**: Posting menu harian (Foto, Nama, Harga, Keterangan).
- **Manajemen Akun**: Membuatkan akun khusus instansi secara manual.
- **Monitoring**: Pelacakan pesanan harian (Siapa & Apa) dan verifikasi pembayaran.

### 4. Modul [ADMIN / SUPER ADMIN] - Manajerial & Kontrol
- **Laporan Laba Rugi**: Rekapitulasi Harian, Mingguan, dan Bulanan.
- **User Control**: Verifikasi pendaftaran "Instansi" yang pending.

## 💰 Logika Harga & Pajak
- **Total = Harga Pokok + Pajak**.
- **Ongkir**: Rp 0.
- **Stok**: Setiap menu memiliki kuota porsi yang berkurang otomatis saat dipesan.

---
*Status: Business Logic Matang (Operational Hours Added)*  
*Last Updated: 2026-04-19*
