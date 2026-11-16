# W3 – Password Cracking & Security Auditing (John The Ripper)

Pentesting Project Report | Networkwalks Cybersecurity Internship

**Author:** Muhammad Rizik Sudrajat
**Batch:** B084K
**Week:** 03
**Date:** 16 November 2026

## 📄 Laporan

Laporan lengkap (semua modul, narasi, risk analysis, recommendations, evidence) ada di:
[`report/Laporan_W3_PM1-PM2_Networkwalks.docx`](./report/Laporan_W3_PM1-PM2_Networkwalks.docx)

## 📦 Modules Completed

| Module | Topik | Tool |
|---|---|---|
| W3-PM1 | Basic Password Cracking & Hash Identification | hash-id, John The Ripper (Dictionary Attack / rockyou.txt) |
| W3-PM2 | Advanced Cracking & Rule-Based Attacks | zip2john, ssh2john, unshadow, John The Ripper (--rules) |

## 📸 Screenshots

Semua screenshot bukti pengerjaan ada di folder [`screenshots/`](./screenshots), dipisah per modul:

- `screenshots/module1-john-basic-cracking/` — identifikasi tipe hash (`hash-id`) dan cracking hash dasar menggunakan `rockyou.txt`
- `screenshots/module2-john-advanced-rules/` — ekstraksi hash (`zip2john` / `ssh2john` / `unshadow`) dan rule-based password cracking (`--rules`)

## ⚠️ Scope & Authorization

Seluruh aktivitas di repo ini dilakukan sesuai Letter of Authorization yang berlaku untuk program internship ini, dan hanya mencakup:
- File hash dummy, arsip terenkripsi, dan kredensial uji coba yang dibuat sendiri di lingkungan virtual lab lokal (Kali Linux)
- Pengujian audit kekuatan password offline sesuai instruksi modul internship

Materi ini murni untuk tujuan edukasi dan riset. Tidak ada percobaan cracking atau akses tanpa izin terhadap sistem maupun akun milik pihak ketiga.

## 📝 Catatan Teknis Menarik

Pada pengujian W3-PM2, kata sandi yang lolos dari *dictionary attack* standar (`rockyou.txt`) ternyata dapat dipecahkan dengan cepat setelah parameter `--rules` diaktifkan. Hal ini membuktikan bahwa sekadar menambahkan kombinasi huruf kapital di awal atau angka/simbol standar di akhir kata (seperti `Admin2026!`) tidak cukup aman terhadap serangan mutasi aturan (*mangling rules*) modern. Detail lengkapnya ada di laporan Bagian 4 dan 5.
