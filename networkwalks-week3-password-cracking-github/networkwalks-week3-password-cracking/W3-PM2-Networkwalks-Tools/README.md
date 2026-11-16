# W3-PM2: Password Cracking with Networkwalks Tools

Dokumentasi teknis untuk **Project Module 2 (W3-PM2)** — Ekstraksi hash PDF secara lokal di peramban dan pengujian *dictionary attack* menggunakan perangkat berbasis web **Networkwalks Hash Calculator** dan **Networkwalks Password Cracker**.

## 🛠️ Spesifikasi Lingkungan & Perangkat

- **Ekstraktor Hash:** Networkwalks Hash Calculator (Client-side Web Crypto / PDF parser)
- **Mesin Dictionary Attack:** Networkwalks Password Cracker
- **Wordlist:** Built-in list (100 common passwords)
- **Berkas Target:** `My-Locked-PDF1.pdf` (AES/RC4 128-bit, Revision R4, Version V4)

## 🔄 Alur Pengerjaan

1. **Ekstraksi Hash Lokal (Browser-Based):**
   - Memproses berkas `My-Locked-PDF1.pdf` pada tab **PDF** di Networkwalks Hash Calculator untuk menghasilkan string hash yang kompatibel dengan `pdf2john` / `hashcat` (tersimpan di [`artifacts/hash_pm2.txt`](./artifacts/hash_pm2.txt)).
2. **Dictionary Attack:**
   - Memasukkan string hash ke Networkwalks Password Cracker dan menjalankan pencocokan menggunakan daftar kata sandi bawaan (100 kata).
   - Kata sandi ditemukan pada percobaan ke-91: **`password1`**.
3. **Verifikasi Dokumen:**
   - Membuka `My-Locked-PDF1.pdf` dengan kata sandi `password1` dan memperoleh flag **`nw{networkwalks_flag1_jtr_270521_1}`**.

## 📎 Referensi Laporan

Lihat dokumentasi lengkap beserta bukti tangkapan layar pada [Laporan Praktikum W3-PM2](../reports/Laporan_Praktikum_W3-PM2_Muhammad_Rizik_Sudrajat.pdf).
