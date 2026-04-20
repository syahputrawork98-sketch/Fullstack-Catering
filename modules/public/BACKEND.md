# Module [PUBLIC] - Backend Atomic Tasks

Fokus pada penyediaan data landing page dan efisiensi akses publik.

## 1. Landing Site Data Engine
- [ ] **Config Retrieval**
    - [ ] Logic fetch data `branding` (Logo/Nama) dari JSON setting.
    - [ ] Logic fetch data `kontak_cs` untuk tombol WA.
- [x] **Data Pre-rendering (SSR)**
    - [x] Integrasi SvelteKit `load` function untuk data Landing Page & Session.
    - [ ] Setup caching headers untuk konten statis (Logo/Banner).

## 2. Global Services
- [ ] **WhatsApp Link Generator**
    - [ ] Helper untuk membangun URL `wa.me` dengan template pesan dinamis.
- [ ] **Public API Guard**
    - [ ] Rate limiting sederhana untuk rute publik guna mencegah bot.
