# 📦 Sistem Inventaris Barang Gudang

![Laravel](https://img.shields.io/badge/Laravel-10.x-red?logo=laravel)
![Vue.js](https://img.shields.io/badge/Vue.js-3.x-green?logo=vue.js)
![MySQL](https://img.shields.io/badge/Database-MySQL-blue?logo=mysql)
![Axios](https://img.shields.io/badge/Axios-HTTP%20Client-yellow?logo=axios)
![jQuery](https://img.shields.io/badge/jQuery-3.x-blue?logo=jquery)
![CSS](https://img.shields.io/badge/CSS-3-blue?logo=css3)
![Status](https://img.shields.io/badge/status-Development-yellow)

> Sistem manajemen gudang berbasis Laravel Blade dengan Vue.js modular, jQuery, Axios, dan dukungan scan barcode/QR. Dirancang untuk mendukung proses manajemen barang secara efisien, real-time, dan aman.

---

## ✨ Fitur Utama

- ✅ Input Barang Masuk & Keluar (Manual + Scan QR/Barcode)
- ✅ Klasifikasi Barang (Sekali Pakai / Bisa Digunakan Kembali)
- ✅ Manajemen Stok Otomatis
- ✅ Riwayat Transaksi & Pelacakan Barang
- ✅ Notifikasi Real-Time via Laravel Reverb + Echo + Vue.js
- ✅ Export Laporan ke PDF & Excel
- ✅ Hak Akses Role (Admin & User)
- ✅ Multi-transaksi simultan

---

## 🧱 Teknologi yang Digunakan

| Layer        | Teknologi                                                                                        |
|--------------|--------------------------------------------------------------------------------------------------|
| Backend      | Laravel 10.x, Laravel Passport (OAuth2), Laravel Reverb (Broadcast Events)                      |
| Frontend     | Laravel Blade (HTML), CSS, JavaScript, **Vue.js (modular)**, **jQuery**, **Axios**              |
| Database     | MySQL                                                                                           |
| Auth         | OAuth2 via Laravel Passport                                                                      |
| Realtime     | Laravel Reverb (Server) + Laravel Echo (Client) + Vue.js for notifications                      |
| Scanner      | HTML5 QR Code Scanner (`html5-qrcode`) / Kamera / USB Barcode Scanner                           |
| Keamanan     | SSL/TLS, Role-based Access Control, reCAPTCHA, OTP (optional)                                    |

---

## 📐 Arsitektur Sistem

```txt
[Browser Client]
   ├─ Laravel Blade (UI)
   ├─ HTML, CSS, JavaScript
   ├─ jQuery / Axios (AJAX)
   └─ Vue.js (Realtime + Scanner)

[Laravel Backend]
   ├─ REST API + Web Routes
   ├─ Auth via Passport (OAuth2)
   └─ Reverb WebSocket Events

[MySQL Database]
