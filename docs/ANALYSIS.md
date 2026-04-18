# Technical Analysis: Fullstack Catering (SvelteKit & Tailwind Stack)

Analisis teknis mendalam mengenai performa, keamanan, dan pengolahan data untuk sistem katering instansi.

## 1. Analisis Performa Mobile & Gambar
- **Auto-Image Optimization**: 
    - Setiap foto yang diunggah CS (modul posting) akan melewati proses kompresi otomatis di sisi server.
    - **Format**: Konversi otomatis ke format **WebP** atau **AVIF** untuk ukuran file terkecil tanpa mengurangi kualitas esensial.
    - **Resolution**: Resizing otomatis ke lebar maksimal 800px (ideal untuk layar mobile).
- **SvelteKit SSR**: Konten katalog harian dimuat di sisi server agar FCP (First Contentful Paint) sangat cepat di handphone.

## 2. Analisis Konkurensi Stok (Concurrency)
- **Tantangan**: Pesanan ganda saat porsi menipis.
- **Solusi**: Penggunaan **PostgreSQL Transaction** dengan isolasi level `SERIALIZABLE` atau `SELECT FOR UPDATE` pada baris stok `DailySchedule`. Ini menjamin porsi tidak akan pernah bernilai negatif meskipun ribuan user menekan tombol checkout secara bersamaan.

## 3. Analisis Pelaporan Keuangan (Laba Rugi)
- **Aggregasi Pesanan**: Laporan laba rugi Harian, Mingguan, dan Bulanan akan dihasilkan menggunakan kueri SQL agregat yang menggabungkan total `base_price` dan `tax`.
- **Siklus Pembatalan**: Logika laporan harus mengabaikan pesanan yang dibatalkan (Cancel) sebelum jam 11:30 atau yang dibatalkan manual oleh admin.

## 4. Analisis Akses & Keamanan (RBAC)
- **Pending Status Mapping**: User kategori "Instansi" yang baru mendaftar akan dikunci di rute dashboard terbatas (tidak bisa checkout harga instansi) sampai statusnya diubah menjadi `ACTIVE` oleh Admin di `hooks.server.js`.

## 5. Analisis Struk PDF
- **Consistency**: Menggunakan `react-pdf/renderer` pada backend untuk menjamin layout struk 80mm tetap konsisten dan tidak bisa diubah-ubah strukturnya oleh user.

---
*Created by: Chief Architecture Governor*  
*Last Updated: 2026-04-19*
