# 🎨 KANBAN FRONTEND - Module [PUBLIC]

Fokus: Branding Gourmet Hub, penemuan menu (discovery), dan alur konversi pengunjung.

---

## 🏗️ UI/UX Atomic Status Board

| Phase | Component / Feature | Atom Detail | Status |
| :--- | :--- | :--- | :--- |
| **01** | **Landing Page** | Premium Hero + Marketing Copy | [x] DONE |
| **05** | **Public Showcase** | Menu Catalog on Home Page | [x] DONE |
| **05** | **Date Scroller** | Global date selection for guests | [x] DONE |
| **07** | **Gourmet Branding** | Global Sync to "Gourmet Hub" | [x] DONE |
| **07** | **CTA Redirection** | "Login to Order" logic on cards | [x] DONE |

---

## 📝 Micro-Atomic Technical Checklist (Learning Resource)

### Phase 01 & 05: Public Discovery (Done)
- [x] **Premium Home Page Showcase**
    - [x] **File**: `src/routes/+page.svelte`.
    - [x] **Integration**: Embed the **Live Menu Catalog** below the hero section.
    - [x] **UX**: Implement Guest-mode overlays for `MenuCard` to encourage login.
- [x] **Date navigation for Guest**
    - [x] **File**: `src/routes/+page.svelte`.
    - [x] **Sync**: Reuse the **Premium Date Scroller** for public menu exploration.

### Phase 07: Visual Finalization (Done)
- [x] **Total System Branding**
    - [x] **Global**: Update all titles, metadata, and logos to **Gourmet Hub**.
- [x] **Unified Footer**
    - [x] **Design**: Modern footer with links to social media and sitemap.

### Phase 07.5: Content Integrity (Done)
- [x] **Navbar Type Alignment**
    - [x] Declare types for public navigation items.
    - [x] Resolve scroll-reactive state types.

### Phase 07.6: UI Creative Design Audit (In Progress)
- [ ] **Landing Page Visual Flow**
    - [ ] Optimization for mobile hero section spacing.
    - [ ] Audit "About Us" section for better readability.

### Phase 08: Puzzle Masa Depan (Planned)
- [ ] **SEO Optimization**
    - [ ] Dynamic JSON-LD for menu items to improve Google search visibility.
- [ ] **Social Proof Section**
    - [ ] Adding customer testimonials or "Most Ordered Today" stats.
