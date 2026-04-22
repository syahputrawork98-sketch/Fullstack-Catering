# ⚙️ KANBAN BACKEND - Module [PUBLIC]

Fokus: Optimalisasi SEO, pemuatan data publik, dan alur pendaftaran personal.

---

## 🏗️ Data Logic Atomic Status Board

| Phase | Logic / API Detail | Atom Detail | Status |
| :--- | :--- | :--- | :--- |
| **09** | **Public Registration** | Personal User INSERT logic | [x] DONE |
| **03** | **Public Data Load** | Anonymous fetch for dailySchedules | [x] DONE |
| **11** | **Sitemap Logic** | URL resolution for menus | [ ] PLANNED |

---

## 📝 Micro-Atomic Technical Checklist (Learning Resource)

### Phase 03: Public Showcase Logic (Done)
- [x] **Guest Catalog Loader**
    - [x] **File**: `src/routes/+page.server.ts`.
    - [x] **Query**: Mirror the dashboard date-resolver.

### Phase 08: Integrity & Security (Done)
- [x] **Guest Path Hardening**
    - [x] Ensure public loaders are optimized and type-safe.
- [x] **Mock Session Implementation**
    - [x] Verified `AUDIT_MODE` persistence.

### Phase 09: Onboarding (Done)
- [x] **Individual Signup Handler**
    - [x] **File**: `src/routes/register/+page.server.ts`.
    - [x] **Security**: Ensure password hashing is applied.

### Phase 11: Puzzle Masa Depan (Planned)
- [ ] **SEO Meta Injection**
    - [ ] Dynamic meta tag population based on today's specials.
- [ ] **Lead Tracking**
    - [ ] Simple logging for guest user clicks.
