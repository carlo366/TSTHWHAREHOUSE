# 📦 Sistem Inventaris Barang Gudang – Laravel 11 + Blade + Vue.js + Reverb

![Laravel](https://img.shields.io/badge/Laravel-11-red?logo=laravel)
![Vue.js](https://img.shields.io/badge/Vue.js-3.x-green?logo=vue.js)
![MySQL](https://img.shields.io/badge/Database-MySQL-blue?logo=mysql)
![Axios](https://img.shields.io/badge/Axios-HTTP-yellow?logo=axios)
![jQuery](https://img.shields.io/badge/jQuery-3.x-blue?logo=jquery)
![CSS](https://img.shields.io/badge/CSS-3-blue?logo=css3)
![Status](https://img.shields.io/badge/status-Development-yellow)

> Aplikasi manajemen gudang modern berbasis Laravel 11 yang menggunakan Blade sebagai frontend utama, Vue.js modular untuk fitur interaktif seperti notifikasi real-time, serta mendukung input data melalui scan QR Code dan Barcode. Sistem ini dirancang untuk efisiensi tinggi dalam mencatat, melacak, dan mengelola stok barang masuk & keluar.

---

## 📝 Deskripsi Umum

Sistem ini bertujuan untuk membantu pengelolaan inventaris gudang dengan menyediakan fitur lengkap mulai dari pencatatan barang masuk dan keluar, pelacakan riwayat pemakaian barang, hingga laporan stok akhir secara real-time. Sistem ini dibangun menggunakan Laravel 11 dengan arsitektur monolitik, di mana Blade digunakan untuk render UI dan Vue.js digunakan secara modular untuk mendukung fungsi-fungsi dinamis.

---

## 🎯 Fitur Utama

### 1. **Manajemen Barang Masuk & Keluar**
- Input barang melalui:
  - Form manual
  - Scan QR Code / Barcode (menggunakan kamera atau USB scanner)
- Informasi lengkap yang dicatat:
  - Nama barang, kategori, jumlah, lokasi penyimpanan, supplier, harga, pengguna, tujuan, dan tanggal

### 2. **Klasifikasi Barang**
- **Barang Sekali Pakai**: langsung habis saat digunakan (misal: kertas, alat tulis)
- **Barang Bisa Dipakai Berulang**: dapat dikembalikan ke gudang setelah digunakan (misal: laptop, bor listrik)

### 3. **Manajemen Stok Otomatis**
- Sistem secara otomatis memperbarui stok saat terjadi transaksi keluar/masuk.
- Membedakan stok aktif, stok dipinjam, dan stok rusak/maintenance.

### 4. **Pelacakan Barang (Tracking)**
- Menampilkan lokasi penyimpanan barang.
- Riwayat pemakaian barang (siapa yang menggunakan, kapan, dan untuk apa).
- Pencarian cepat via kategori, nama, atau barcode.

### 5. **Laporan & Statistik**
- Laporan barang masuk & keluar berdasarkan tanggal, kategori, supplier, atau pemakai.
- Estimasi penggunaan bulanan.
- Grafik barang terpakai terbanyak.
- Export laporan ke **PDF** dan **Excel**.

---

## ⚙️ Teknologi & Tools

| Layer           | Teknologi                                                                 |
|-----------------|---------------------------------------------------------------------------|
| Framework       | Laravel 11 (backend & Blade frontend)                                     |
| Interaktivitas  | Vue.js modular (Realtime + QR scanner), JavaScript, jQuery, Axios         |
| Database        | MySQL                                                                     |
| Autentikasi     | Laravel Passport (OAuth2)                                                 |
| Realtime System | Laravel Reverb (Server) + Laravel Echo (Client) + Vue.js (Notifikasi)     |
| QR Scanner      | HTML5 QR Scanner (`html5-qrcode`, Webcam, atau USB Barcode Reader)        |
| Keamanan        | SSL/TLS, Login, reCAPTCHA, Role-based Access Control, Optional OTP        |

---

## 🏗️ Arsitektur Aplikasi

```txt
+-------------------+        Scan/Input/Notif        +---------------------+
|   Frontend (UI)   |  <---------------------------> |    Laravel Backend  |
| - Blade Templates |                               | - Routes & Controllers
| - JavaScript      |                               | - Laravel Echo & Events
| - Vue Components  |                               | - Passport Auth
+-------------------+                               +---------------------+
         |                                                       |
         | REST/HTTP & WebSocket                                 |
         v                                                       v
+---------------------------+                       +-----------------------+
|        User Browser       |                       |     MySQL Database     |
| - Scan via Camera         |                       | - Table Barang         |
| - Real-time Notif Display |                       | - Table Transaksi      |
+---------------------------+                       | - Table Pengguna       |
                                                    +-----------------------+
