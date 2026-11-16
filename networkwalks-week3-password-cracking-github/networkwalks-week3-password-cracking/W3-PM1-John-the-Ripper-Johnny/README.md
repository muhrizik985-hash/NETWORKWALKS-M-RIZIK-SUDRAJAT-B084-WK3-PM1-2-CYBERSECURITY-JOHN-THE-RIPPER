# W3-PM1: Password Cracking with John the Ripper (JTR) & Johnny GUI

Dokumentasi teknis untuk **Project Module 1 (W3-PM1)** — Ekstraksi hash dan pemulihan kata sandi dokumen PDF terenkripsi menggunakan **John the Ripper** dan **Johnny GUI** di lingkungan Windows.

## 🛠️ Spesifikasi Lingkungan & Perangkat

- **Sistem Operasi:** Windows (64-bit)
- **Mesin Cracking:** John the Ripper `1.9.0-jumbo-1` (64-bit Windows binaries)
- **Antarmuka Grafis:** Johnny GUI `v2.2`
- **Ekstraktor Hash:** Online PDF Hash Extractor (`pdf2john` compatible format)
- **Berkas Target:** `My Locked PDF1.pdf`

## 🔄 Alur Pengerjaan

1. **Instalasi & Integrasi Mesin JTR:**
   - Mengekstrak paket biner `john-1.9.0-jumbo-1-win64` dan memasang `johnnyInstaller.exe`.
   - Menghubungkan executable `run/john.exe` pada menu **Settings** Johnny hingga terdeteksi `Detected John the Ripper 1.9.0-jumbo-1 OMP`.
2. **Ekstraksi String Hash PDF:**
   - Mengekstrak metadata enkripsi berkas `My Locked PDF1.pdf` menjadi format string `$pdf$4*4*128*...` dan menyimpannya ke dalam [`artifacts/hash.txt`](./artifacts/hash.txt).
3. **Eksekusi Password Cracking:**
   - Memuat `hash.txt` melalui menu **Open password file (PASSWD format)** di Johnny GUI dan menjalankan serangan (**Start new attack**).
   - Kata sandi berhasil dipulihkan: **`good-luck`**.
4. **Verifikasi Dokumen:**
   - Membuka `My Locked PDF1.pdf` menggunakan kata sandi `good-luck` dan memvalidasi flag **`nw{cybersecurity_flag_captured_2608}`**.

## 📎 Referensi Laporan

Lihat dokumentasi lengkap beserta bukti tangkapan layar pada [Laporan Praktikum W3-PM1](../reports/Laporan_Praktikum_W3-PM1_Muhammad_Rizik_Sudrajat.pdf).
