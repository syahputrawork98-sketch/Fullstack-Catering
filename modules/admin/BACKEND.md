# Module [ADMIN / SUPER ADMIN] - Backend Atomic Tasks

Fokus pada agregasi laporan keuangan, manajemen kontrol user, dan sistem audit.

## 1. User Management (CRUD)
- [ ] **Account Control**
    - [ ] **Create**: Logic pembuatan akun Admin/CS baru.
    - [ ] **Read**: Fetching daftar semua user (dengan filter role/status).
    - [ ] **Update**: Edit data user atau reset password oleh admin.
    - [ ] **Delete**: Soft-delete atau penonaktifan akun user/staff.
- [ ] **Registration Approval Workflow**
    - [ ] Endpoint `PATCH` untuk aktivasi akun "Pending Instansi".

## 2. Global System Config (CRUD)
- [ ] **Tax & Identity Service**
    - [ ] **Read**: Mengambil data pajak & branding saat ini.
    - [ ] **Update**: Simpan perubahan PPN (Pajak) atau Logo ke database.
- [ ] **Email System**
    - [ ] **Update**: Konfigurasi kredensial SMTP/Email.

## 3. Financial Reporting Engine
- [ ] **Daily/Weekly/Monthly Aggregator**
    - [ ] SQL Query: `SUM(grand_total)` per Day/Week/Month.
- [ ] **Excel/CSV Export Service**
    - [ ] Generator dokumen laporan.

## 4. Audit & Security
- [ ] **Audit Logging Middleware**
    - [ ] System Capture: Pencatatan otomatis aktivitas CRUD yang dilakukan Admin.
