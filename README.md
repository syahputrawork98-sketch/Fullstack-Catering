# Fullstack Catering: Internal Instansi Hub

Sistem manajemen katering terintegrasi yang dirancang khusus untuk operasional katering instansi. Fokus pada performa mobile, manajemen porsi harian, dan pelaporan keuangan yang akurat.

## 🚀 Tech Stack
- **Frontend/Fullstack Framework**: [SvelteKit](https://kit.svelte.dev/) (Mobile-optimized, Zero Virtual DOM).
- **Styling**: [Tailwind CSS](https://tailwindcss.com/) (Responsive & Modern UI).
- **Icons & Components**: Bits UI / Skeleton per Svelte standards.
- **Database**: PostgreSQL.
- **ORM**: Drizzle ORM (Type-safe & Scalable).
- **Authentication**: Auth.js (Integrated SvelteKit Auth).

## 📂 Project Structure
Proyek ini terbagi menjadi 4 modul utama dengan hak akses terpisah (RBAC):
1.  **Public**: Landing page & panduan pemesanan.
2.  **User/Customer**: Katalog menu harian, Checkout, & Riwayat Pesanan.
3.  **Customer Service (CS)**: Posting menu, verifikasi pembayaran, & bantuan input.
4.  **Admin**: Laporan Laba Rugi (H/M/B) & Manajemen User.

## 📝 Modular Progress Trackers (Atomic Tasks)
Gunakan link di bawah ini untuk memantau detail pengerjaan Front-end dan Back-end di setiap modul:

| Module | Frontend Checklist | Backend Checklist |
| :--- | :--- | :--- |
| **Public** | [FRONTEND.md](modules/public/FRONTEND.md) | [BACKEND.md](modules/public/BACKEND.md) |
| **User** | [FRONTEND.md](modules/user/FRONTEND.md) | [BACKEND.md](modules/user/BACKEND.md) |
| **CS** | [FRONTEND.md](modules/cs/FRONTEND.md) | [BACKEND.md](modules/cs/BACKEND.md) |
| **Admin** | [FRONTEND.md](modules/admin/FRONTEND.md) | [BACKEND.md](modules/admin/BACKEND.md) |

## 🗺️ Development Roadmap
- [x] **Phase 1: Blueprint & Analysis** (Business Logic, Architecture, Database Schema).
- [x] **Phase 2: Project Initialization** (SvelteKit Setup, Tailwind 4, DB Sync & Docker).
- [/] **Phase 3: Auth & RBAC Implementation** (Registration, Login Logic, JWT Strategy - *Enabled*).
- [/] **Phase 4: UI Framework & Dashboards** (Premium Landing Page, User/Admin/CS Layouts).
- [ ] **Phase 5: Core Features (Daily Menu & Ordering)** (Catalog, Cart, Atomic Stock).
- [ ] **Phase 6: Operational & Reporting** (CS Dashboard, Admin Finance Reports).

---
*Created with discipline by the Chief Architecture Governor.*