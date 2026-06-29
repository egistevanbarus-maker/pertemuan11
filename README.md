# Stevan Store - Client Integration Catalog Aplikasi E-Commerce

Aplikasi mobile Android/iOS berbasis **React Native** dan **Expo Framework** yang mengonsumsi REST API publik secara dinamis. Aplikasi ini mengintegrasikan katalog produk komprehensif dengan sistem manajemen state yang adaptif, penanganan galat (*robust error handling*), filter lokal tingkat lanjut, serta dibalut dalam antarmuka modern bertema *Midnight Dark Mode* (`#0f172a`) dengan konversi mata uang otomatis ke Rupiah (Rp).

---

## 👤 Identitas Pengembang
Aplikasi ini dibangun dan dikembangkan untuk memenuhi syarat penugasan praktikum pemrograman mobile oleh:

| **Nama Lengkap** : Egi Stevan Barus
| **NIM** : 243303621266 
| **Program Studi** : Sistem Informasi 
| **Fakultas** : Fakultas Sains dan Teknologi |
| **Universitas** : Universitas Prima Indonesia

---

## 🌐 API yang Digunakan
Aplikasi ini terintegrasi secara *real-time* dengan endpoint publik gratis tanpa API Key:
- **Target API:** [FakeStore API - Products Endpoint](https://fakestoreapi.com/products)
- **Data Model:** Mengambil array objek produk yang mencakup gambar (`image`), judul (`title`), harga asli dalam USD (`price`), rating (`rating.rate`), dan kategori (`category`).

---

## 🛠️ Tech Stack & Arsitektur

- **Core Framework:** React Native (Expo Workflow)
- **Language Standard:** JavaScript / ES6+
- **State Management:** React Hooks (`useState`, `useEffect`, `useMemo`)
- **Data Fetching:** Native JavaScript Fetch API dengan pola `Async/Await`
- **Styling Architecture:** React Native StyleSheet API (Responsive Grid layout & Dark Palette)

---

## 🗂️ Daftar Fitur Aplikasi

### 🟢 Level 1 — Fitur Wajib (Core) [Selesai]
- [x] **Async/Await REST API Request:** Proses pengambilan data dari server secara asynchronous.
- [x] **useEffect Mount Guard:** Fetching data dieksekusi tepat satu kali saat komponen pertama kali dimuat (`dependency array []`).
- [x] **3-State Kondisi UI:** Manajemen tampilan adaptif yang menangani kondisi saat data dimuat (*Loading* via `ActivityIndicator`), kegagalan jaringan (*Error*), dan data berhasil dirender (*Success*).
- [x] **Safe Block Handling (`try/catch/finally`):** Struktur penanganan galat yang aman, memastikan state *loading* selalu dimatikan di blok `finally` apa pun skenarionya.
- [x] **Optimized FlatList Grid:** Menampilkan kumpulan data menggunakan `FlatList` dengan optimasi properti `keyExtractor` dan render kartu dalam format 2 kolom (*numColumns*).
- [x] **Multi-Field Item Card:** Setiap kartu produk menampilkan minimal 4 informasi: Gambar, Judul, Kategori, Harga (Rupiah), dan Rating Bintang.
- [x] **Functional Retry Button:** Tombol "Coba Lagi" pada layar *error state* yang secara fungsional memicu pemanggilan kembali fungsi *fetching* API ke server tanpa harus memuat ulang seluruh aplikasi.

### 🟡 Level 2 & 🔴 Level 3 — Fitur Pengembangan Pilihan [Selesai]
- [x] **🔄 Pull-to-Refresh (Level 2):** Fitur geser ke bawah pada daftar untuk memicu pemuatan ulang (*refetching*) data katalog secara langsung menggunakan komponen `RefreshControl`.
- [x] **🔎 Client-Side Search / Filter (Level 2):** Kolom `TextInput` interaktif untuk menyaring daftar produk berdasarkan judul secara instan di memori lokal (*zero latency*).
- [x] **🗂️ Filter Kategori via Horizontal Chips (Level 2):** Barisan menu kategori berbentuk *chips* yang dapat digeser secara horizontal untuk menyortir jenis barang (Elektronik, Pakaian, Perhiasan).
- [x] **🎨 Interactive Empty State UI (Level 2):** Tampilan khusus fallback dengan ilustrasi ikon pencarian jika kombinasi pencarian kata kunci atau filter kategori tidak menghasilkan produk sama sekali (*bukan layar blank*).
- [x] **📈 Advanced Price Sorting (Level 3 - Bonus):** Fitur pengurutan produk secara lokal berdasarkan harga terendah (`Murah`) ke tertinggi (`Mahal`) ataupun kembali ke mode normal.

---

## 📱 Dokumentasi Screenshot (Expo Go)

Berikut adalah bukti uji coba fungsionalitas 3-State UI yang berjalan pada perangkat fisik:

| 1. Loading State | 2. Success State | 3. Error State |
| :---: | :---: | :---: |
| ![Loading State](https://placehold.co/300x600/0f172a/38bdf8?text=Loading+State\n[ActivityIndicator]) | ![Success State](https://placehold.co/300x600/0f172a/f8fafc?text=Success+State\n[Katalog+Kategori+Rupiah]) | ![Error State](https://placehold.co/300x600/0f172a/ef4444?text=Error+State\n[Retry+Button]) |

> *Catatan: Ganti tautan placeholder gambar di atas dengan screenshot asli dari HP fisik kamu saat pengumpulan.*

---

## 💻 Cara Menjalankan Proyek Secara Lokal

Pastikan Anda telah memasang [Node.js](https://nodejs.org/) di perangkat Anda, kemudian ikuti instruksi berikut:

1. **Clone repositori ini ke komputer lokal Anda:**
   ```bash
   git clone [https://github.com/USERNAME_KAMU/NAMA_REPOSITORY.git](https://github.com/USERNAME_KAMU/NAMA_REPOSITORY.git)
   cd NAMA_REPOSITORY
