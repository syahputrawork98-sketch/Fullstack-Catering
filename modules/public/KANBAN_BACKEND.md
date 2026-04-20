# ⚙️ KANBAN BACKEND - Module [PUBLIC]

Fokus: Optimalisasi SEO, pemuatan data publik, dan alur pendaftaran personal.

---

## 🏗️ Data Logic Atomic Status Board

| Phase | Logic / API Detail | Atom Detail | Status |
| :--- | :--- | :--- | :--- |
| **02** | **Public Registration** | Personal User INSERT logic | [x] DONE |
| **05** | **Public Data Load** | Anonymous fetch for dailySchedules | [x] DONE |
| **05** | **Sitemap Logic** | URL resolution for menus | [ ] PLANNED |

---

## 📝 Micro-Atomic Technical Checklist (Learning Resource)

### Phase 02: Onboarding (Done)
- [x] **Individual Signup Handler**
    - [x] **File**: `src/routes/register/+page.server.ts`.
    - [x] **Mod**: Update to handle `PUBLIK` registration as the only public path.
    - [x] **Security**: Ensure password hashing is applied even for retail users.

### Phase 05: Public Showcase Logic (Done)
- [x] **Guest Catalog Loader**
    - [x] **File**: `src/routes/+page.server.ts`.
    - [x] **Query**: Mirror the dashboard date-resolver to fetch menus for anonymous visitors.
    - [x] **Perf**: Ensure query is lean (only necessary fields for the landing page).

### Phase 07.5: Public Security (Done)
- [x] **Guest Path Hardening**
    - [x] Ensure public loaders for `/packages` and `/` are optimized and type-safe.

### Phase 07.6: UI Audit Enablement (In Progress)
- [ ] **Global Layout Audit**
    - [ ] Audit responsive behavior of the new `PublicNavbar`.

### Phase 08: Puzzle Masa Depan (Planned)
- [ ] **SEO Meta Injection**
    - [ ] Dynamic meta tag population based on today's specials.
- [ ] **Lead Tracking**
    - [ ] Simple logging to see which menus Guest users click most.
