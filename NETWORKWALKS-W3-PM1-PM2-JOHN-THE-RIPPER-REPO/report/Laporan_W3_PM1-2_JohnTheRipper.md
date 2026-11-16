# LAPORAN PRAKTIKUM CYBERSECURITY - WEEK 3 (PM1 & PM2)
## Topik: John The Ripper (Password Cracking & Auditing)

---

### **Identitas Praktikan**
- **Nama:** M. Rizik Sudrajat
- **Batch Internship:** B084
- **Program:** NetworkWalks Cybersecurity Internship

---

## **MODUL 1: Basic Password Cracking & Hash Identification**

### **1. Tujuan Pembelajaran**
- Memahami konsep dasar serangan *password cracking* menggunakan John the Ripper (JtR).
- Mampu mengidentifikasi jenis algoritma *hash* password menggunakan tools pendukung (`hash-id` / `john`).
- Melakukan *dictionary attack* menggunakan *wordlist* standar (`rockyou.txt`).

### **2. Langkah Kerja & Praktikum**
1. **Identifikasi Hash:**
   Menganalisis format *hash* target untuk menentukan parameter format yang tepat di John the Ripper.
   ```bash
   hash-id '5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8'
   ```
2. **Menjalankan Basic Cracking:**
   Menjalankan perintah John the Ripper dengan wordlist `rockyou.txt` pada file hash target.
   ```bash
   john --wordlist=/usr/share/wordlists/rockyou.txt target_hash.txt
   ```
3. **Melihat Hasil (Show Cracked Passwords):**
   ```bash
   john --show target_hash.txt
   ```

---

## **MODUL 2: Advanced Cracking & Rule-Based Attacks**

### **1. Tujuan Pembelajaran**
- Menggunakan fitur *rules* bawaan John the Ripper untuk memodifikasi *wordlist* (variasi huruf kapital, angka, simbol).
- Melakukan *cracking* pada file arsip terenkripsi (ZIP/RAR) atau SSH private keys.
- Memahami penggunaan *incremental mode* saat wordlist standar tidak mencukupi.

### **2. Langkah Kerja & Praktikum**
1. **Ekstraksi Hash dari File (Contoh: ZIP / SSH):**
   Mengubah format file arsip/kunci privat menjadi format yang bisa dibaca oleh John the Ripper.
   ```bash
   zip2john secure_archive.zip > zip_hash.txt
   ssh2john id_rsa > ssh_hash.txt
   ```
2. **Menjalankan Rule-Based Attack:**
   Menggunakan aturan modifikasi lanjutan agar John menguji variasi kata sandi yang lebih kompleks.
   ```bash
   john --wordlist=/usr/share/wordlists/rockyou.txt --rules zip_hash.txt
   ```
3. **Verifikasi Hasil:**
   Memastikan kata sandi berhasil di-crack dan didokumentasikan ke dalam laporan.

---

## **Kesimpulan**
John the Ripper merupakan tool yang sangat kuat dan fleksibel untuk melakukan audit keamanan sandi (*password auditing*). Melalui praktikum PM1 dan PM2 ini, dipahami pentingnya menerapkan kebijakan pembuatan kata sandi yang kuat (panjang, kombinasi huruf besar/kecil, angka, dan simbol) agar tahan terhadap metode *dictionary* maupun *rule-based attack*.
