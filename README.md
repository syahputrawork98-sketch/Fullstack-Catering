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
- [ ] **Phase 2: Project Initialization** (NextJS/SvelteKit Setup, Tailwind config, DB Migration).
- [ ] **Phase 3: Auth & RBAC Implementation** (Login, Register Pending Instansi, Middleware).
- [ ] **Phase 4: Core Features (Daily Menu & Ordering)** (Catalog, Cart, Atomic Stock).
- [ ] **Phase 5: Operational & Reporting** (CS Dashboard, Image Optimization, Admin Finance Reports).
- [ ] **Phase 6: Final Polish & Deployment** (PDF Struk, Audit Log, Production Build).

---
*Created with discipline by the Chief Architecture Governor.*