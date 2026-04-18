# Project Architecture: Fullstack Catering (SvelteKit Hub)

Arsitektur ini memanfaatkan kecepatan **SvelteKit** dan fleksibilitas **Tailwind CSS** untuk menciptakan pengalaman mobile-responsive yang premium.

## 🛠️ Modern Tech Stack
- **Framework**: **SvelteKit**. Dipilih karena performa tinggi di perangkat mobile (Zero Virtual DOM).
- **Styling**: **Tailwind CSS**. Digunakan untuk desain yang Mobile-First dan responsive.
- **Components**: **Bits UI / Skeleton**. Memberikan sentuhan estetika premium (Rich Aesthetics).
- **Database**: **PostgreSQL**. Untuk integritas data transaksi dan laporan.
- **ORM**: **Drizzle ORM** atau **Prisma**. Menjamin sinkronisasi skema data yang aman.
- **Auth**: **Auth.js** (SvelteKit Integration).

## 📁 System Modules (Routing Layout)

### 1. Rute Publik (`src/routes/`)
- `+page.svelte`: Landing page utama (Informasi & Panduan).
- `/login`: Halaman pintu masuk (Auth-wall).

### 2. Rute Terproteksi (`src/routes/(authenticated)/`)
Menggunakan Grouping Route untuk keamanan terpusat:
- `/dashboard`: Modul **User** (Katalog, Checkout, History).
- `/cs`: Modul **Customer Service** (Posting Menu, Order Tracking).
- `/admin`: Modul **Admin** (Reporting & User Management).

## 🔄 Core Data Flow
- **Server Loaders**: Data menu diambil di sisi server (`+page.server.js`) sebelum dikirim ke HP user untuk load yang instan.
- **Form Actions**: Pengolahan pesanan menggunakan aksi native SvelteKit untuk keamanan dan skalabilitas tinggi.
- **Postgres Hooks**: Verifikasi stok harian (Supply vs Demand) dilakukan langsung di level query database.

## 📱 Mobile-First Strategy
- Semua komponen (Button, Card Menu, Cart) didesain untuk lebar layar handphone terlebih dahulu.
- Gambar menu dioptimalkan (lazy loading) agar hemat kuota data pelanggan.

---
*Created by: Chief Architecture Governor*  
*Last Updated: 2026-04-19 (Stack: SvelteKit + Tailwind)*
