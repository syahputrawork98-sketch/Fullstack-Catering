# 🗺️ Project Workspace Map & Migration Guide

> [!IMPORTANT]
> This file serves as the **Master Link** between the project's **Brain** (Planning) and its **Muscles** (Execution).

## 🏗️ Current Architecture (Pre-Migration)
- **Root Repository (`Fullstack-Catering`)**: Perencanaan, Blueprint, & Progres.
- **Backend Folder (`catering-backend`)**: [TO BE DELETED] - Redundant boilerplate.
- **Execution Folder (`catering-frontend`)**: [TO BE RENAMED] - Active full-stack project.

---

## 🎯 Intended Architecture (Post-Migration)
Setelah migrasi manual oleh User, struktur akan mengikuti skema berikut:

### 1. The Brain (Root / Brain Hub)
Berisi seluruh dokumentasi operasional dan standar prosedur (SOP).
- `/modules/`: SOP Frontend & Backend per aktor (User/CS/Admin).
- `/docs/`: Dokumentasi teknis tambahan.
- `PROGRESS.md`: Arus progres fitur global.
- `WORKFLOW.md`: Standar pengerjaan (7-Step Unified Master SOP).

### 2. The Muscles (Execution / Application)
Folder tunggal untuk seluruh kode aplikasi.
- **Folder Path**: `/app` (Dulu: `catering-frontend`)
- **Technology**: SvelteKit 5 (Full-stack).
- **Database**: Drizzle ORM + PostgreSQL.

---

## 🚦 Instructions for AI (Future Context)
Jika AI mendeteksi root repo ini, **selalu prioritaskan** folder `/app` sebagai pusat eksekusi kode. Jika folder `/app` belum ditemukan, maka folder `catering-frontend` adalah folder target sementara hingga user selesai merubah namanya.
