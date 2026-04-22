# 🎨 KANBAN FRONTEND - Module [USER / CUSTOMER]

Fokus: Pengalaman pengguna mobile-first, estetika premium **Gourmet Hub**, dan reaktivitas Svelte 5.

---

## 🏗️ UI/UX Atomic Status Board

| Phase | Component / Feature | Atom Detail | Status |
| :--- | :--- | :--- | :--- |
| **09** | **Registration UI** | Name, Phone, Role Toggle | [x] DONE |
| **09** | **Login UI** | Secure Input + Error Toasts | [x] DONE |
| **08** | **User Dashboard** | Welcome Header + Stats Grid | [x] DONE |
| **04** | **Menu Grid** | Responsive Columns (2-4) | [x] DONE |
| **04** | **Menu Card** | Image, Stock, Price Format | [x] DONE |
| **04** | **Cart Drawer** | Sliding Layout + Persistence | [x] DONE |
| **02** | **Order Stepper** | Visual Timeline (4 Stages) | [x] DONE |
| **02** | **Digital Receipt** | 80mm Branded PDF Output | [x] DONE |
| **03** | **Daily Catalog** | Horizontal Date Scroller | [x] DONE |
| **03** | **Stock Awareness** | "Sold Out" Overlay & Grayscale | [x] DONE |
| **04** | **Cart Persistence** | localStorage + Delivery Date Bind | [x] DONE |

---

## 📝 Micro-Atomic Technical Checklist (Learning Resource)

### Phase 02: Logistics & PDF (Done)
- [x] **Order Stepper Component**
    - [x] Visual timeline for order tracking.
- [x] **Thermal Receipt Engine**
    - [x] **File**: `src/lib/utils/pdfGenerator.ts`.
    - [x] **Library**: Initialize `jsPDF` for 80mm format.

### Phase 03: Core Catalog (Done)
- [x] **Premium Date Scroller**
    - [x] **File**: `src/routes/dashboard/menu/+page.svelte`.
    - [x] **UI**: Build horizontal `snap-x` scroller for 7-day navigation.
- [x] **Stock-Aware Menu Card**
    - [x] **File**: `src/lib/components/MenuCard.svelte`.
    - [x] **Logic**: Implement `{#if stock === 0}` overlay with "Habis Terjual" label.

### Phase 04: Ordering & Cart (Done)
- [x] **B2C Order Submission**
    - [x] **File**: `src/routes/dashboard/checkout/+page.svelte`.
    - [x] **Logic**: Bind `deliveryDate` from catalog to the checkout form.
- [x] **Cart Persistence**
    - [x] localStorage sync for cart items.

### Phase 08: Integrity & Design Audit (Done)
- [x] **Svelte 5 Syntax Audit**
    - [x] Resolve "Unexpected Token" errors in `checkout/+page.svelte`.
- [x] **User Portal Aesthetic Audit**
    - [x] Refine date scroller visuals and layout consistency.

### Phase 09 & 10: Auth & Architecture (Polishing)
- [x] **Registration Form Implementation**
    - [x] **File**: `src/routes/register/+page.svelte`.
- [x] **Login Page Implementation**
    - [x] **File**: `src/routes/login/+page.svelte`.

### Phase 11: Puzzle Masa Depan (Planned)
- [ ] **Loyalty Points UI**
    - [ ] Display "Gourmet Points" earned per transaction.
- [ ] **Subscription Status UI**
    - [ ] Add badge for active catering subscription tier.

