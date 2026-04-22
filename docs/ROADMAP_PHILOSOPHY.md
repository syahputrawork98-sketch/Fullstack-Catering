# 🧠 Roadmap Philosophy: Feature-First, Security-Ready

Dokumen ini menjelaskan strategi urutan pengerjaan fitur untuk menjaga kecepatan iterasi dan menghindari hambatan "Sistem Terkunci" oleh Auth/RBAC di tahap awal.

---

## 🏗️ Strategi Urutan Pengerjaan

Rekomendasi urutan pengerjaan yang ideal agar pengembangan tidak terasa "berat" atau "greget":

### 1. Dasar (Infrastruktur)
Membangun pondasi database, docker, dan struktur folder. 
*Status: Harus di awal.*

### 2. Nilai Utama (Fitur Fungsional)
Membangun fitur yang langsung memberikan nilai bisnis tanpa peduli siapa yang mengaksesnya.
- Katalog Menu, Pemesanan (Cart), Struk PDF, Laporan Keuangan.
- **Teknik Dev**: Gunakan `MOCK_USER` atau `BYPASS_AUTH` agar bisa testing tanpa login.

### 3. Logika Bisnis Lanjutan
- Audit Logs, Manajemen Stok Otomatis, Sinkronisasi Stok.
- Di sini data mulai kompleks, tapi akses masih dibuka luas untuk mempermudah debugging.

### 4. Pengamanan (Auth & RBAC) - **TAHAP AKHIR**
Memasang pintu dan satpam.
- Pendaftaran, Login, Proteksi Route (Admin vs CS vs User).
- Ini adalah tahap "Final Polish" sebelum sistem dianggap siap produksi.

---

## 🔐 Emergency Bypass Protocol (Dev-Only)

Jika selama pengerjaan fitur Anda merasa "Terkunci" oleh sistem Login/RBAC, gunakan protokol ini di file `src/hooks.server.ts`:

```typescript
// Contoh Bypass di Hooks
if (process.env.NODE_ENV === 'development') {
    // Paksa user menjadi ADMIN secara otomatis
    event.locals.user = { id: 'dev-id', role: 'ADMIN' }; 
    return resolve(event);
}
```

## 🎯 Kesimpulan
Membangun "Otot" (Fitur) harus lebih didahulukan daripada membangun "Pintu" (Auth). Dengan begitu, kita bisa memastikan aplikasi berfungsi dengan baik sebelum kita menentukan siapa yang boleh membukanya.

---
*Filosofi ini disepakati untuk menjaga kewarasan Developer dan kecepatan iterasi proyek.*
