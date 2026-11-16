# 🔐 Password Cracking & PDF Security Auditing (Week 3: W3-PM1 & W3-PM2)

> **Deskripsi Singkat:** Dokumentasi dan hasil praktikum *Cybersecurity & Ethical Hacking Internship* (NetworkWalks) untuk menguji kekuatan enkripsi berkas PDF yang dilindungi kata sandi menggunakan metode ekstraksi *hash* dan serangan *password cracking* (berbasis desktop lokal maupun berbasis web).

---

## 📋 Daftar Isi

* [Tentang Proyek](#-tentang-proyek)
* [Rincian Modul Praktikum](#-rincian-modul-praktikum)
  * [Modul 1 (W3-PM1): John the Ripper & Johnny GUI](#modul-1-w3-pm1-john-the-ripper--johnny-gui)
  * [Modul 2 (W3-PM2): Networkwalks Web Tools](#modul-2-w3-pm2-networkwalks-web-tools)
* [Ringkasan Hasil & Flag](#-ringkasan-hasil--flag)
* [Tools & Teknologi](#-tools--teknologi)
* [Panduan Reproduksi Langkah](#-panduan-reproduksi-langkah)
* [Struktur Repositori](#-struktur-repositori)
* [Kesimpulan & Rekomendasi Keamanan](#-kesimpulan--rekomendasi-keamanan)
* [Praktikan](#-praktikan)

---

## 📖 Tentang Proyek

Repositori ini berisi dokumentasi lengkap dari rangkaian tugas praktikum **Week 3 (Project Module 1 & Project Module 2)** pada program **NetworkWalks Cybersecurity & Ethical Hacking Internship**. Fokus utama dari praktikum ini adalah memahami bagaimana struktur enkripsi pada dokumen PDF dapat diekstrak menjadi format *hash* (`$pdf$...`), serta bagaimana kerentanan kata sandi diuji menggunakan teknik pemulihan kata sandi (*password cracking*).

### Tujuan Utama:
1. Mengekstrak nilai *hash* enkripsi dari dokumen PDF yang terkunci (`My Locked PDF1.pdf` / `My-Locked-PDF1.pdf`).
2. Melakukan audit dan pemulihan kata sandi menggunakan perangkat *open-source* di lingkungan lokal (**John the Ripper** & **Johnny GUI**).
3. Melakukan pengujian serangan kamus (*dictionary attack*) berbasis peramban menggunakan **Networkwalks Hash Calculator** dan **Networkwalks Password Cracker**.
4. Memverifikasi akses dokumen dan mengambil *flag* sebagai bukti keberhasilan audit.

---

## 🧩 Rincian Modul Praktikum

### Modul 1 (W3-PM1): John the Ripper & Johnny GUI

Pada modul pertama (`W3-PM1 - Essential`), proses audit keamanan dilakukan secara lokal pada sistem operasi Windows dengan mengombinasikan mesin *cracking* **John the Ripper (JTR)** dan antarmuka visual **Johnny GUI**.

* **Alur Kerja:**
  1. Mengunduh paket biner `John the Ripper 1.9.0-jumbo-1 (64-bit Windows)` dan memasang `Johnny GUI v2.2`.
  2. Menghubungkan *executable* `john.exe` (`.../run/john.exe`) pada menu *Settings* di Johnny GUI hingga terdeteksi status `Detected John the Ripper 1.9.0-jumbo-1 OMP`.
  3. Mengekstrak string *hash* dari berkas `My Locked PDF1.pdf` menggunakan layanan *Online PDF Hash Extractor* (`onlinehashcrack.com`).
  4. Menyimpan string *hash* (`$pdf$4*4*128*...`) ke dalam berkas teks murni bernama `hash.txt`.
  5. Memuat `hash.txt` ke Johnny GUI (`Open password file > PASSWD format`) dan menjalankan serangan melalui tombol **Start new attack**.
* **Hasil:** Kata sandi berhasil dipulihkan (`good-luck`) dan membuka akses dokumen beserta kode *flag*.

---

### Modul 2 (W3-PM2): Networkwalks Web Tools

Pada modul kedua (`W3-PM2 - Essential`), proses ekstraksi *hash* dan serangan kamus (*dictionary attack*) dilakukan sepenuhnya melalui peramban (*browser-based*) tanpa memerlukan instalasi perangkat lunak tambahan di komputer lokal.

* **Alur Kerja:**
  1. Mengunduh berkas target `My-Locked-PDF1.pdf` dari halaman lab resmi NetworkWalks.
  2. Membuka **Networkwalks Hash Calculator** (`networkwalks.com/hash-calculator/`), memilih tab **PDF**, dan mengunggah berkas target untuk mem-parsing *hash* secara lokal di peramban (`Revision: R4 | Version: V4 | Key Length: 128 bit`).
  3. Menyalin string *hash* yang kompatibel dengan `pdf2john` / `hashcat`.
  4. Membuka **Networkwalks Password Cracker** (`networkwalks.com/password-cracker/`), menempelkan string *hash*, dan memilih kamus kata sandi bawaan (**Built-in list - 100 passwords**).
  5. Menekan tombol **START CRACKING** untuk mencocokkan *hash* dengan daftar kata sandi.
* **Hasil:** Kata sandi berhasil ditemukan pada percobaan ke-91 dari 100 kata (`password1`) dengan kecepatan pemrosesan rata-rata $\approx 9\text{ pw/s}$.

---

## 🏆 Ringkasan Hasil & Flag

| Modul | Metode / Tools | Berkas Target | Password Ditemukan | Flag yang Diperoleh |
| :--- | :--- | :--- | :--- | :--- |
| **W3-PM1** | JTR 1.9.0-jumbo-1 + Johnny GUI v2.2 | `My Locked PDF1.pdf` | `good-luck` | `nw{cybersecurity_flag_captured_2608}` |
| **W3-PM2** | Networkwalks Hash Calculator & Cracker | `My-Locked-PDF1.pdf` | `password1` | `nw{networkwalks_flag1_jtr_270521_1}` |

---

## 🛠 Tools & Teknologi

* **Sistem Operasi:** Windows (64-bit)
* **Desktop Auditing Tools:**
  * [John the Ripper (1.9.0-jumbo-1 Win64)](https://www.openwall.com/john/)
  * [Johnny GUI (v2.2)](https://openwall.info/wiki/john/johnny)
* **Web-Based Auditing Tools:**
  * [Online Hash Crack - PDF Hash Extractor](https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php)
  * [Networkwalks Hash Calculator](https://networkwalks.com/hash-calculator/)
  * [Networkwalks Password Cracker](https://networkwalks.com/password-cracker/)

---

## 🚀 Panduan Reproduksi Langkah

Jika ingin mereproduksi pengujian pada **Modul 1 (Lokal)**:

1. Ekstrak folder biner `john-1.9.0-jumbo-1-win64` dan instal `johnnyInstaller.exe`.
2. Simpan *hash* target ke dalam file `hash.txt`:
   ```text
   $pdf$4*4*128*-1028*1*16*ca7f72f11459cba469f1005a8765ed51*32*f32d8fa1bfbe2648226dffc39f7909ea0021446990b9e4114071a4d9104984c1*32*9322f50c29569712067a775264635e4954ccb1b99e209d664984054ffad30a6a
   ```
3. Buka **Johnny**, arahkan *path* *executable* pada tab **Settings** ke `.../run/john.exe`.
4. Pilih **Open password file (PASSWD format)** $\rightarrow$ pilih `hash.txt` $\rightarrow$ klik **Start new attack**.

---

## 📁 Struktur Repositori

```text
networkwalks-w3-password-cracking/
├── W3-PM1_John-The-Ripper/
│   ├── hash.txt                                                      # Hasil ekstraksi hash PDF Modul 1
│   └── Laporan Praktikum Week 3 - Project Module 1 (W3-PM1).pdf      # Laporan lengkap Modul 1
├── W3-PM2_Networkwalks-Tools/
│   └── Laporan Praktikum Week 3 - Project Module 2 (W3-PM2).pdf      # Laporan lengkap Modul 2
└── README.md                                                         # Dokumentasi utama proyek
```

---

## 💡 Kesimpulan & Rekomendasi Keamanan

1. **Kerentanan Kata Sandi Umum:** Pengujian pada kedua modul membuktikan bahwa dokumen dengan enkripsi 128-bit sekalipun tetap dapat ditembus dalam hitungan detik apabila menggunakan kata sandi yang pendek, umum, atau terdaftar di dalam kamus (*wordlist*) seperti `good-luck` dan `password1`.
2. **Mitigasi:** Untuk melindungi kerahasiaan dokumen sensitif, gunakan kata sandi yang panjang (minimal 12–16 karakter) dengan kombinasi huruf besar, huruf kecil, angka, dan simbol acak yang tidak membentuk kata dalam kamus.

---

## 👤 Praktikan

* **Nama:** Muhammad Rizik Sudrajat
* **Asal Instansi:** SMK Wikrama Bogor
* **Program:** NetworkWalks Cybersecurity & Ethical Hacking Internship (Week 3)

> *Disclaimer: Seluruh aktivitas ekstraksi hash dan pemulihan kata sandi dalam repositori ini dilakukan secara sah dalam lingkungan lab edukasi resmi milik NetworkWalks.*