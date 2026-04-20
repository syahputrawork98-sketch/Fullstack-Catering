# 🎨 KANBAN FRONTEND - Module [USER / CUSTOMER]

Fokus: Pengalaman pengguna mobile-first, estetika premium **Gourmet Hub**, dan reaktivitas Svelte 5.

---

## 🏗️ UI/UX Atomic Status Board

| Phase | Component / Feature | Atom Detail | Status |
| :--- | :--- | :--- | :--- |
| **02** | **Registration UI** | Name, Phone, Role Toggle | [x] DONE |
| **02** | **Login UI** | Secure Input + Error Toasts | [x] DONE |
| **03** | **User Dashboard** | Welcome Header + Stats Grid | [x] DONE |
| **04** | **Menu Grid** | Responsive Columns (2-4) | [x] DONE |
| **04** | **Menu Card** | Image, Stock, Price Format | [x] DONE |
| **04** | **Cart Drawer** | Sliding Layout + Persistence | [x] DONE |
| **04** | **Order Stepper** | Visual Timeline (4 Stages) | [x] DONE |
| **04** | **Digital Receipt** | 80mm Branded PDF Output | [x] DONE |
| **05** | **Daily Catalog** | Horizontal Date Scroller | [x] DONE |
| **05** | **Stock Awareness** | "Sold Out" Overlay & Grayscale | [x] DONE |
| **06** | **Cart Persistence** | localStorage + Delivery Date Bind | [x] DONE |

---

## 📝 Micro-Atomic Technical Checklist (Learning Resource)

### Phase 02: Authentication UI (Done)
- [x] **Registration Form Implementation**
    - [x] **File**: `src/routes/register/+page.svelte`.
    - [x] **State**: Define `$state(false)` for tracking `loading` during form submission.
    - [x] **Logic**: Remove category selector (Personal only) for public signup.
    - [x] **Branding**: Sync logo and typography to **Gourmet Hub**.
- [x] **Login Page Implementation**
    - [x] **File**: `src/routes/login/+page.svelte`.
    - [x] **Logic**: Extract success message from URL params (`registered=true`).

### Phase 03, 04 & 05: UI & Catalog (Done)
- [x] **Gourmet Hub Dashboard Hub**
    - [x] **File**: `src/routes/dashboard/+page.svelte`.
    - [x] **Overview**: Implement "Aksi Hari Ini" overview status.
- [x] **Thermal Receipt Engine**
    - [x] **File**: `src/lib/utils/pdfGenerator.ts`.
    - [x] **Library**: Initialize `jsPDF` for 80mm format.
- [x] **Premium Date Scroller**
    - [x] **File**: `src/routes/dashboard/menu/+page.svelte`.
    - [x] **UI**: Build horizontal `snap-x` scroller for 7-day navigation.
    - [x] **Logic**: Use `selectedDate` derived from URL params to highlight active day.
- [x] **Stock-Aware Menu Card**
    - [x] **File**: `src/lib/components/MenuCard.svelte`.
    - [x] **Logic**: Implement `{#if stock === 0}` overlay with "Habis Terjual" label.
    - [x] **Visual**: Apply `grayscale` and `opacity-50` to images with zero stock.

### Phase 06: Ordering & Cart (Done)
- [x] **B2C Order Submission**
    - [x] **File**: `src/routes/dashboard/checkout/+page.svelte`.
    - [x] **Logic**: Bind `deliveryDate` from catalog to the checkout form.
    - [x] **UX**: Automatic cart clearing on success using `cart.clear()` in `<form use:enhance>`.

### Phase 07.5: UI Integrity (Done)
- [x] **Svelte 5 Syntax Audit**
    - [x] Resolve "Unexpected Token" errors in `checkout/+page.svelte`.
    - [x] Audit all `$props()` usage to ensure total Svelte 5 compliance.
- [x] **Type-Safe Prop Management**
    - [x] Update `MenuCard.svelte` to use strict types for `basePrice` and `image`.

### Phase 07.6: UI Creative Design Audit (In Progress)
- [ ] **User Portal Aesthetic Audit**
    - [ ] Refine date scroller visuals and layout consistency.
    - [ ] Audit Menu Cards for desktop larger screens.

### Phase 08: Puzzle Masa Depan (Planned)
- [ ] **Loyalty Points UI**
    - [ ] Display "Gourmet Points" earned per transaction.
- [ ] **Subscription Status UI**
    - [ ] Add badge for active catering subscription tier.
