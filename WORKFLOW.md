# 📖 Unified Master SOP (Standard Operating Procedure)

Dokumen ini mendefinisikan alur kerja hibrida yang menggabungkan perencanaan strategis dengan eksekusi teknis yang terstruktur.

---

## 🔄 Siklus 7-Langkah Emas

Setiap fitur atau perubahan besar dalam proyek ini wajib melewati 7 tahap berikut secara urut:

### 1. 🧠 [PLANNING] Diskusi & Analisis
- Menyelaraskan visi bisnis dengan User.
- Menganalisis dampak teknis pada sisi Frontend dan Backend.
- Menentukan skema data atau tipe yang dibutuhkan.

### 2. 📋 [PLANNING] Task Creation
- Menyusun daftar tugas (Checklist) yang sangat detail.
- Membagi tugas menjadi sub-tugas Frontend, Backend, dan Dokumentasi.

### 3. 🛑 [GATE] Review User (STOP)
- **AI Wajib Berhenti**. Menampilkan Task List kepada User untuk ditinjau.
- Tidak boleh ada pengerjaan kode sebelum User memberikan persetujuan ("lakukan").

### 4. 🎨 [EXECUTION] Frontend-First
- Membangun UI/UX menggunakan standar **Vibrant Gourmet**.
- Menggunakan data mockup agar desain bisa langsung diuji secara visual.

### 5. 📝 [SYNC] Dokumentasi Tahap I (UI)
- Memperbarui status di `modules/*/KANBAN_FRONTEND.md`.
- Mencatatkan progres visual di `PROGRESS_KANBAN_MASTER.md`.

### 6. ⚙️ [EXECUTION] Backend & Integrasi
- Implementasi logika server, API, dan Database (Drizzle).
- Menghubungkan data asli ke UI yang sudah dibangun di tahap 4.

### 7. 📝 [SYNC] Dokumentasi Tahap II (Final)
- Memperbarui `modules/*/KANBAN_BACKEND.md`.
- Memperbarui status final di `PROGRESS_KANBAN_MASTER.md` dan Roadmap di `README.md`.

---
*Protokol ini adalah kesatuan hukum tertinggi dalam pengerjaan proyek Fullstack Catering.*
