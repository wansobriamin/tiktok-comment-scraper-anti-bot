# TikTok Comment Scraper

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Playwright](https://img.shields.io/badge/Playwright-Chromium-green)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-yellow)
![OpenPyXL](https://img.shields.io/badge/OpenPyXL-XLSX%20Support-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

**TikTok Comment Scraper** adalah proyek Python untuk mengambil data komentar dari video TikTok secara otomatis menggunakan **Playwright**.

Proyek ini dibuat agar bisa mengumpulkan komentar dalam jumlah besar, misalnya lebih dari 1000 komentar, lalu menyimpannya ke dalam file `.csv` atau `.xlsx` supaya mudah diolah sebagai penelitian.

Hasil scraping berisi kolom:

| Kolom | Penjelasan |
|---|---|
| `uid` | ID unik pengguna yang meninggalkan komentar |
| `username` | Username akun yang berkomentar |
| `komentar` | Isi komentar |
| `like` | Jumlah like pada komentar |

### Scraping Komentar TikTok Otomatis

Scraper ini bekerja dengan membuka halaman video TikTok menggunakan browser Chromium, lalu mengambil data komentar secara otomatis.
Proses scraping tidak hanya membaca HTML statis, tetapi juga menangkap respons API komentar yang muncul saat halaman TikTok dimuat dan di-scroll.
Untuk menghadapi sistem anti-bot TikTok, scraper ini menggunakan pendekatan hybrid, yaitu kombinasi antara kerja otomatis mesin dan intervensi manual apabila muncul captcha atau verifikasi manusia.

### Kelebihan
1. lolos dari anti-bot
2. Mendukung Pengambilan Lebih dari 1000 Komentar
3. tidak perlu login ulang setiap kali run
4. profil browser lebih mirip pengguna asli
5. export file yang flexible bisa pilih file `.csv` atau `.xlsx`

## Struktur Project

```text
tiktok-comment-scraper/
│
├── scraping_tiktok_comment.ipynb         # Notebook utama scraper
├── README.md                             # Dokumentasi project
├── requirements.txt                      # Dependency Python
├── .gitignore                            # File yang tidak ikut di-push ke Git
│
├── tiktok_profile/                       # Profil browser Chromium, jangan di-commit
│
└── output/                               # Folder hasil scraping, opsional
    ├── username_date.csv
    └── username_date.xlsx
```

## Cara Penggunaan

### 1. Buka Notebook

Buka file:

```text
scraping_tiktok_comment.ipynb
```

menggunakan VS Code atau Jupyter Notebook.

### 2. Jalankan Cell Instalasi

Jalankan cell berikut jika belum pernah install:

```python
!pip install playwright pandas openpyxl
!playwright install chromium
```

### 3. Atur Konfigurasi

Di bagian konfigurasi, ubah URL video TikTok yang ingin di-scrape:

```python
VIDEO_URL = "https://www.tiktok.com/@username/video/123456789..."
```

Tentukan jumlah komentar:

```python
MAX_COMMENTS = 1000
```

Pilih format ekspor:

```python
EXPORT_FORMAT = "csv"
```

atau:

```python
EXPORT_FORMAT = "xlsx"
```

### 4. Jalankan Cell Utama

- Jalankan cell scraper utama.

- Browser Chromium akan terbuka otomatis.

- Jika muncul captcha, verifikasi manusia, atau halaman login, selesaikan secara manual di browser yang terbuka.

- Tunggu mesin memproses selanjutnya

- Setelah itu scraper akan melanjutkan proses, lakukan scroll untuk pengambilan komentar.


## Catatan Etika Scraping

Project ini dibuat untuk tujuan edukasi, analisis data publik, riset, dan pengembangan pribadi.

Saat menggunakan scraper ini, harap perhatikan hal berikut:

1. Hormati Terms of Service Platform

2. Ambil Hanya Data Publik

3. Jangan Beban Server Berlebih

4. Perhatikan Privasi Data

5. Tanggung Jawab Pengguna

---

## Lisensi

Project ini dapat digunakan untuk keperluan edukasi saja.

Copyright (c) 2026 wansobriamin
