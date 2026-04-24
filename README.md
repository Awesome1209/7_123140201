## 👨‍💻 Identitas Mahasiswa
* **Nama**: Awi Septian Prasetyo
* **NIM**: 123140201
* **Program Studi**: Teknik Informatika, Institut Teknologi Sumatera
---
# Notes App - Local Data Storage (Week 7)

Proyek ini adalah pengembangan aplikasi catatan (Notes App) berbasis **Kotlin Multiplatform (KMP)** yang mengimplementasikan sistem penyimpanan data lokal yang aman dan reaktif. Proyek ini memenuhi tugas pertemuan ke-7 untuk mata kuliah Pengembangan Aplikasi Mobile di **Institut Teknologi Sumatera**.

## 📝 Deskripsi Tugas
Tujuan utama dari tugas ini adalah meng-upgrade aplikasi catatan dengan fitur penyimpanan permanen menggunakan **SQLDelight** untuk database relasional dan **DataStore** untuk preferensi pengguna.

## 🚀 Fitur Utama
* **Manajemen Catatan (CRUD)**: Menambah, membaca, memperbarui, dan menghapus catatan secara lokal.
* **Fitur Pencarian**: Mencari catatan berdasarkan judul atau isi konten secara efisien.
* **Pengaturan Aplikasi (Settings)**: Mengubah tema aplikasi (Light/Dark) dan urutan sortir yang tersimpan secara permanen melalui DataStore.
* **Offline-First Architecture**: Aplikasi menggunakan database lokal sebagai sumber utama data (*Single Source of Truth*), sehingga tetap berfungsi tanpa koneksi internet.
* **UI Reaktif**: Menggunakan *UI State* yang tepat untuk menangani kondisi *loading*, data kosong, maupun saat menampilkan konten.

## 🗄️ Skema Database (SQLDelight)
Penyimpanan data utama menggunakan SQLDelight yang menghasilkan API Kotlin yang *type-safe*. Berikut adalah skema tabel yang digunakan:

```sql
CREATE TABLE Note (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    title TEXT NOT NULL,
    content TEXT NOT NULL,
    created_at INTEGER NOT NULL
);
```

### Operasi Database:
* `selectAll`: Mengambil semua catatan diurutkan berdasarkan waktu pembuatan terbaru.
* `insert`: Menambahkan catatan baru ke dalam database.
* `update`: Memperbarui data catatan yang sudah ada.
* `delete`: Menghapus catatan berdasarkan ID unik.
* `search`: Mencari catatan menggunakan kata kunci tertentu.

## 🛠️ Stack Teknologi
* **SQLDelight**: Untuk manajemen database SQLite di berbagai platform (Android & iOS).
* **Multiplatform Settings (DataStore)**: Untuk penyimpanan *key-value* pada pengaturan aplikasi.
* **Kotlin Coroutines & Flow**: Untuk menangani data secara asinkron agar UI tetap responsif.
* **Repository Pattern**: Sebagai abstraksi untuk mengelola sumber data.

## 📸 Screenshots
*(Lampirkan hasil tangkapan layar aplikasi Anda di sini sesuai instruksi)*

| Notes List | Search Feature | Settings Screen |
| :--- | :--- | :--- |
| ![List](url_gambar) | ![Search](url_gambar) | ![Settings](url_gambar) |

## 🎥 Demo Video
Video berdurasi 45 detik yang menunjukkan fungsionalitas CRUD, pencarian, pengaturan tema, dan mode offline dapat diakses melalui tautan di bawah ini:
**[Link Video Demo Anda]** 

---
---

Apakah Anda ingin saya menambahkan bagian teknis yang lebih spesifik, seperti cara melakukan *setup* `DatabaseDriverFactory` untuk Android dan iOS?
