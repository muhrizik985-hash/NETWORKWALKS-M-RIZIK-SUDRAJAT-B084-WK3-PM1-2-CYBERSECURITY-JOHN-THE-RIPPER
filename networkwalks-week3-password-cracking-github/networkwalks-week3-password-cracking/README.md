# 🔐 NetworkWalks Cybersecurity & Ethical Hacking Internship — Week 3

![Program](https://img.shields.io/badge/Program-NetworkWalks_Internship-0A66C2?style=for-the-badge)
![Module](https://img.shields.io/badge/Week_3-Password_Cracking-DC2626?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-16A34A?style=for-the-badge)

Dokumentasi teknis, laporan praktikum resmi, dan artefak pengujian keamanan untuk tugas **Week 3 (Project Module 1 & Project Module 2)** pada program **NetworkWalks Cybersecurity & Ethical Hacking Internship**.

---

## 👤 Informasi Praktikan

| Atribut | Keterangan |
| :--- | :--- |
| **Nama** | Muhammad Rizik Sudrajat |
| **Instansi** | SMK Wikrama Bogor (Teknik Jaringan Komputer dan Telekomunikasi) |
| **Program** | NetworkWalks Cybersecurity & Ethical Hacking Internship |
| **Topik** | PDF Encryption Hash Extraction & Password Auditing |

---

## 📂 Struktur Repositori

```text
networkwalks-week3-password-cracking/
├── README.md                                                    # Dokumentasi utama repositori
├── .gitignore                                                   # Konfigurasi pengecualian file sementara
├── reports/                                                     # Laporan praktikum lengkap (PDF)
│   ├── Laporan_Praktikum_W3-PM1_Muhammad_Rizik_Sudrajat.pdf
│   └── Laporan_Praktikum_W3-PM2_Muhammad_Rizik_Sudrajat.pdf
├── W3-PM1-John-the-Ripper-Johnny/                               # Modul 1: JTR & Johnny GUI
│   ├── README.md
│   └── artifacts/
│       └── hash.txt
└── W3-PM2-Networkwalks-Tools/                                   # Modul 2: NetworkWalks Web Tools
    ├── README.md
    └── artifacts/
        └── hash_pm2.txt
```

---

## 📊 Ringkasan Hasil Praktikum

| Modul | Judul Praktikum | Perangkat / Tools | Target Berkas | Kata Sandi Ditemukan | Flag |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **[W3-PM1](./W3-PM1-John-the-Ripper-Johnny/)** | Password Cracking with John the Ripper & Johnny GUI | John the Ripper `1.9.0-jumbo-1`, Johnny GUI `v2.2`, Online PDF Hash Extractor | `My Locked PDF1.pdf` | `good-luck` | `nw{cybersecurity_flag_captured_2608}` |
| **[W3-PM2](./W3-PM2-Networkwalks-Tools/)** | Password Cracking with Networkwalks Tools | Networkwalks Hash Calculator, Networkwalks Password Cracker | `My-Locked-PDF1.pdf` | `password1` | `nw{networkwalks_flag1_jtr_270521_1}` |

---

## 📄 Dokumen Laporan Resmi

Seluruh tahapan instalasi, konfigurasi, tangkapan layar (*screenshot*) proses ekstraksi hash, pengujian serangan kata sandi, hingga verifikasi hasil terdokumentasi secara lengkap dalam berkas laporan berikut:

- 📑 **[Laporan Praktikum W3-PM1 (PDF)](./reports/Laporan_Praktikum_W3-PM1_Muhammad_Rizik_Sudrajat.pdf)**
- 📑 **[Laporan Praktikum W3-PM2 (PDF)](./reports/Laporan_Praktikum_W3-PM2_Muhammad_Rizik_Sudrajat.pdf)**

---

## 🛡️ Analisis Keamanan & Mitigasi

1. **Kerentanan Kata Sandi Lemah:** Kata sandi yang pendek atau masuk dalam daftar kamus kata sandi umum (*wordlist*) seperti `good-luck` dan `password1` dapat dipulihkan dalam hitungan detik menggunakan serangan berbasis kamus (*dictionary attack*) maupun aturan mutasi (*rule-based attack*).
2. **Rekomendasi Pengamanan Dokumen:**
   - Gunakan *passphrase* minimal 12–16 karakter yang menggabungkan huruf kapital, huruf kecil, angka, dan simbol acak.
   - Terapkan standar enkripsi PDF modern (**AES-256** / PDF 2.0) untuk meningkatkan kompleksitas komputasi saat proses verifikasi kunci.

---

## ⚠️ Disclaimer

Seluruh aktivitas ekstraksi hash dan pemulihan kata sandi dalam repositori ini dilakukan secara sah dalam lingkungan laboratorium terkendali untuk tujuan edukasi dan audit keamanan siber (*ethical hacking*).
