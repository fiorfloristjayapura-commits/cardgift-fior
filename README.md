# 🎁 FIOR Florist - Card Gift Generator

![FIOR Logo](https://img.shields.io/badge/FIOR-Card%20Gift%20Generator-gold)
![Version](https://img.shields.io/badge/Version-1.0.0-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Live-brightgreen)

Sistem otomatis untuk membuat dan mengirim kartu ucapan digital sebagai pelengkap layanan florist FIOR.

## 🔗 Live Demo
- **Admin Panel:** [https://fiorfloristjayapura-commits.github.io/cardgift-fior/](https://fiorfloristjayapura-commits.github.io/cardgift-fior/)
- **Contoh Kartu:** [https://fiorfloristjayapura-commits.github.io/cardgift-fior/card.html](https://fiorfloristjayapura-commits.github.io/cardgift-fior/card.html)

## ✨ Fitur Utama

### 🎨 **Pembuatan Kartu**
- 6+ tema kartu (Valentine, Birthday, Wedding, dll)
- Personalisasi nama penerima & pesan
- Preview real-time
- Desain responsif & elegan

### 📱 **Integrasi WhatsApp**
- Kirim langsung ke WhatsApp customer
- Format pesan otomatis
- Tombol satu-klik untuk pengiriman

### 🗃️ **Manajemen Data**
- Database customer di Google Sheets
- Riwayat semua kartu yang dibuat
- Pencarian & filter customer
- Auto-complete form

### ⚡ **Fitur Admin**
- Dashboard yang user-friendly
- Statistik sederhana
- Multi-device support
- Export data (coming soon)

## 🏗️ Arsitektur Sistem

─────────────────┐ ┌──────────────────┐ ┌─────────────────┐
│ Admin Panel │────▶│ Google Apps Script│────▶│ Google Sheets │
│ (Frontend) │ │ (Backend) │ │ (Database) │
└─────────────────┘ └──────────────────┘ └─────────────────┘
│ │ │
▼ ▼ ▼
GitHub Pages Data Processing Data Storage
(Hosting) & API Handling & Logging


## 📁 Struktur Repository
cardgift-fior/
├── index.html # Main admin interface
├── card.html # Template kartu ucapan
├── README.md # Dokumentasi ini
├── .gitignore # Git ignore rules
├── assets/ # Resource files
│ ├── css/ # Stylesheets
│ ├── js/ # JavaScript files
│ ├── images/ # Gambar & icons
│ └── fonts/ # Font files
└── docs/ # Dokumentasi tambahan


## 🚀 Cara Menggunakan

### Untuk Admin:
1. **Login ke Admin Panel** di URL GitHub Pages
2. **Pilih atau tambah customer** dari database
3. **Tulis pesan personal** untuk customer
4. **Pilih tema kartu** yang sesuai
5. **Generate & kirim** via WhatsApp

### Workflow Lengkap:
```mermaid
graph LR
    A[Pilih Customer] → B[Isi Pesan]
    B → C[Pilih Tema]
    C → D[Generate Kartu]
    D → E[Kirim WA]
    E → F[Selesai]

⚙️ Setup & Instalasi
Prasyarat:
Akun Google (untuk Sheets & Apps Script)
Akun GitHub (untuk hosting)
Spreadsheet dengan 2 sheet:
customers - Data pelanggan
cards - Riwayat kartu

Langkah Setup:
1. Setup Google Sheets
// Buat spreadsheet baru dengan:
// Sheet 1: customers
// Kolom: Timestamp, Nama, WhatsApp, Catatan

// Sheet 2: cards  
// Kolom: Timestamp, Nama, Tema, Pesan, Link, Status

2. Setup Google Apps Script
Buka spreadsheet → Extensions → Apps Script
Salin kode dari Code.gs
Deploy sebagai Web App dengan setting:
Execute as: Me
Who has access: Anyone

3. Setup GitHub Repository
# Clone repository
git clone https://github.com/fiorfloristjayapura-commits/cardgift-fior.git
# Atau upload manual melalui GitHub web interface

4. Konfigurasi URL
Edit index.html:
// Line ~90-91
const SCRIPT_URL = "https://script.google.com/macros/s/YOUR_SCRIPT_ID/exec";
const CARD_BASE_URL = "https://fiorfloristjayapura-commits.github.io/cardgift-fior/card.html";

🎨 Tema Tersedia
Tema	Icon	Warna	Kegunaan
Valentine	❤️	Merah Muda	Hari Kasih Sayang
Birthday	🎂	Biru Cerah	Ulang Tahun
Condolence	🕊️	Abu-abu	Belasungkawa
Anniversary	💑	Ungu	Hari Jadi
Wedding	💍	Emas	Pernikahan
Graduation	🎓	Hijau	Wisuda
Buat styling di card.html untuk tema baru

Ubah Warna Brand:
css
/* Di bagian CSS, ubah variabel: */
:root {
  --primary: #d4af37;    /* Warna emas FIOR */
  --secondary: #1a1a1a;  /* Background */
  --accent: #4ecdc4;     /* Warna aksen */
}

Tambah Field Data:
Tambah input di form HTML

Update struktur Google Sheets

Modifikasi Google Apps Script

🐛 Troubleshooting Guide
Common Issues:
Masalah	Penyebab	Solusi
Data tidak tersimpan	URL Script salah	Periksa & update SCRIPT_URL
Customer kosong	Sheet tidak ada	Buat sheet 'customers'
WA tidak terbuka	Format nomor salah	Gunakan format 62xxx
CORS error	Deployment setting	Deploy dengan 'Anyone' access
Load lama	Cache browser	Ctrl+F5 / Clear cache
Debug Mode:
Aktifkan developer console (F12) untuk melihat error:

javascript
// Tambahkan di kode untuk debugging
console.log('Current data:', data);
localStorage.setItem('debug', 'true');
📊 Best Practices
Untuk Admin:
Backup data secara berkala

Update customer list setiap ada order baru

Gunakan tema yang sesuai dengan occasion

Personalize pesan untuk customer tetap

Untuk Maintenance:
Test sistem setelah update

Monitor Google Quotas (Apps Script limits)

Keep dependencies updated

Document changes di README

🔒 Security & Privacy
✅ No sensitive data stored in frontend

✅ Google secured backend

✅ HTTPS only (GitHub Pages)

✅ Rate limiting by Google

⚠️ Public script URL - keep it secret

📈 Roadmap
Version 1.1 (Next)
Bulk card generation

Template management

Analytics dashboard

CSV import/export

Version 1.2 (Planned)
SMS integration

Email campaigns

Customer segmentation

Advanced reporting

Future Ideas
Mobile app version

API for external systems

AI message suggestions

Social media sharing

👥 Kontribusi
Kontribusi diterima! Ikuti langkah:

Fork repository

Buat feature branch (git checkout -b feature/improvement)

Commit changes (git commit -m 'Add some feature')

Push to branch (git push origin feature/improvement)

Open Pull Request

Guidelines:
Gunakan Bahasa Indonesia untuk komentar

Test sebelum commit

Update dokumentasi jika perlu

Ikuti style code yang ada

📞 Support & Contact
Issues: GitHub Issues

Email: admin@fiorflorist.com

Website: fiorflorist.com

Location: Jayapura, Papua

🙏 Credits & Acknowledgments
Dikembangkan oleh: Tim FIOR Florist Jayapura
Design: Custom UI/UX untuk florist
Technology Stack: HTML5, CSS3, JavaScript, Google Apps Script
Special Thanks: All our customers for the inspiration

📄 License
MIT License © 2024 FIOR Florist Jayapura

text
"Menghubungkan emosi dengan bunga dan teknologi"
🚀 Quick Deployment
bash
# Untuk deploy cepat:
1. Buat Google Sheets dengan struktur di atas
2. Deploy Google Apps Script
3. Upload file ke GitHub
4. Enable GitHub Pages
5. Update URLs di index.html
6. Test sistem
⭐ Support project ini dengan memberikan star! ⭐
🔗 Share dengan florist lain jika bermanfaat! 🔗

text

## 🎯 **TL;DR Version untuk README.md:**

```markdown
# FIOR Card Gift Generator

Live: https://fiorfloristjayapura-commits.github.io/cardgift-fior/

## Setup:
1. Buat Google Sheets dengan sheet: customers & cards
2. Deploy Google Apps Script (Code.gs)
3. Upload ke GitHub Pages
4. Update SCRIPT_URL di index.html

## Features:
- Create digital cards
- WhatsApp integration  
- Google Sheets database
- 6+ card themes
- Admin dashboard

## Support:
Issues: GitHub Issues | Email: admin@fiorflorist.com
Pilih versi yang sesuai. Versi lengkap baik untuk dokumentasi publik, versi ringkas untuk quick reference. Sesuaikan email dan contact information dengan data Anda yang sebenarnya.


