# Penjelasan NIST Special Publication 1800-35E: Implementing a Zero Trust Architecture

## Informasi Dokumen

**Judul Lengkap:** NIST Special Publication 1800-35E - Implementing a Zero Trust Architecture, Volume E: Risk and Compliance Management

**Status:** Preliminary Draft (Draf Pendahuluan)

**Tanggal Publikasi:** Desember 2022

**Penulis:**
- Alper Kerman
- Murugiah Souppaya
- Karen Scarfone
- Susan Symington
- William Barker

**Kata Kunci:** Zero Trust (ZT), Zero Trust Architecture (ZTA), Cybersecurity, Compliance, Risk Management, NIST Cybersecurity Framework (CSF), Executive Order 14028, NIST SP 800-53

---

## Ringkasan Eksekutif

Dokumen ini merupakan Volume E dari seri panduan NIST tentang implementasi Zero Trust Architecture (ZTA). Berbeda dengan volume lainnya yang fokus pada aspek teknis implementasi, Volume E secara khusus ditujukan untuk **manajer risiko** dan **petugas kepatuhan** (compliance officers).

Tujuan utama dokumen ini adalah membantu organisasi mendemonstrasikan bagaimana implementasi ZTA dapat memenuhi persyaratan kepatuhan regulasi dan standar manajemen risiko yang ada.

---

## Struktur Dokumen

Dokumen terdiri dari **65 halaman** yang terbagi dalam beberapa bagian utama:

### 1. Halaman Pembuka
- Judul dan abstrak
- Disclaimer dan mekanisme feedback
- Kata pengantar
- Ucapan terima kasih

### 2. Bagian 1: Introduction (Pendahuluan)
Menjelaskan tujuan panduan dan hubungannya dengan volume lain dalam seri (Volume A hingga E).

### 3. Bagian 2: Risk Management (Manajemen Risiko)
Fokus pada ancaman, kerentanan, dan risiko dalam ekosistem IT modern.

### 4. Bagian 3: ZTA Reference Architecture Security Mappings
**Inti dari dokumen** - Memetakan fungsi-fungsi ZTA ke standar keamanan yang sudah ada.

### 5. References (Referensi)
Daftar pustaka dan dokumen pendukung.

### 6. Appendix (Lampiran)
Daftar akronim dan singkatan.

---

## Topik-Topik Utama

### A. Fokus Khusus Volume E: Risk and Compliance Management

> [!IMPORTANT]
> Volume E berbeda dari volume lainnya karena tidak fokus pada eksekusi teknis, melainkan pada **aspek manajerial** dari implementasi ZTA.

**Target Audiens:**
- Manajer Risiko
- Compliance Officers (Petugas Kepatuhan)
- CISO dan eksekutif keamanan siber
- Auditor

**Tujuan Utama:**
Membantu organisasi membuktikan kepada auditor dan regulator bahwa implementasi ZTA bukan sekadar tren teknologi, tetapi merupakan metodologi yang dapat memenuhi standar keamanan internasional.

---

### B. Manajemen Risiko (Section 2)

#### 2.1 Ancaman (Threats)

Dokumen menyoroti **perubahan paradigma** dalam lingkungan kerja modern:

**Perubahan Lanskap Kerja:**
- ✅ Karyawan bekerja dari mana saja (Work From Anywhere - WFA)
- ✅ Penggunaan berbagai perangkat (laptop, smartphone, tablet)
- ✅ Akses dari lokasi yang tidak terprediksi
- ❌ Batas jaringan tradisional tidak lagi relevan

**Implikasi Keamanan:**
Model keamanan berbasis perimeter (firewall di tepi jaringan) tidak lagi efektif karena:
- Pengguna bisa berada di dalam atau di luar jaringan perusahaan
- Perangkat pribadi (BYOD) digunakan untuk mengakses data perusahaan
- Aplikasi cloud berada di luar kontrol infrastruktur tradisional

#### 2.2 Kerentanan (Vulnerabilities)

**Masalah Utama: Implicit Trust (Kepercayaan Implisit)**

Pada model keamanan tradisional:
```
Setelah masuk ke jaringan → Dipercaya sepenuhnya → Dapat mengakses banyak resource
```

**Risiko:**
- Jika penyerang berhasil menembus perimeter (misalnya melalui phishing), mereka dapat bergerak bebas di dalam jaringan (*lateral movement*)
- Konsep "castle and moat" (benteng dan parit) tidak lagi aman
- Tidak ada verifikasi berkelanjutan setelah autentikasi awal

#### 2.3 Solusi ZTA

**Prinsip-Prinsip ZTA:**

1. **Never Trust, Always Verify (Jangan Pernah Percaya, Selalu Verifikasi)**
   - Tidak ada kepercayaan implisit berdasarkan lokasi jaringan
   - Setiap permintaan akses harus diverifikasi

2. **Least Privilege Access (Akses Paling Terbatas)**
   - Hanya memberikan akses minimum yang diperlukan
   - Akses diberikan berdasarkan identitas, kredensial, dan otorisasi yang kuat

3. **Assume Breach (Anggap Telah Diretas)**
   - Merancang sistem dengan asumsi bahwa pelanggaran dapat terjadi
   - Meminimalkan "blast radius" (radius dampak) jika terjadi pembobolan

**Cara ZTA Memitigasi Risiko:**
- ✅ Verifikasi berkelanjutan untuk setiap sesi
- ✅ Segmentasi mikro (micro-segmentation)
- ✅ Monitoring dan logging yang komprehensif
- ✅ Enkripsi end-to-end
- ✅ Pengurangan area serangan (attack surface)

---

### C. Pemetaan Keamanan (Section 3)

> [!NOTE]
> Bagian ini adalah **inti** dari dokumen dan menyediakan tabel-tabel detail untuk compliance mapping.

#### 3.1 Tiga Framework Utama

Dokumen memetakan karakteristik ZTA ke tiga kerangka kerja keamanan utama:

##### 1. **NIST Cybersecurity Framework (CSF)**

NIST CSF memiliki lima fungsi utama:
- **Identify (ID)** - Identifikasi aset dan risiko
- **Protect (PR)** - Implementasi kontrol keamanan
- **Detect (DE)** - Deteksi insiden keamanan
- **Respond (RS)** - Respons terhadap insiden
- **Recover (RC)** - Pemulihan dari insiden

**Contoh Pemetaan:**
- Fungsi ZTA → Subkategori CSF (seperti ID.AM untuk Asset Management, PR.AC untuk Access Control)

##### 2. **NIST SP 800-53 (Security and Privacy Controls)**

Memetakan komponen ZTA ke kontrol keamanan spesifik, seperti:
- **AC-2:** Account Management (Manajemen Akun)
- **AC-3:** Access Enforcement (Penegakan Akses)
- **AC-4:** Information Flow Enforcement (Penegakan Aliran Informasi)
- **AU-6:** Audit Review, Analysis, and Reporting
- **IA-2:** Identification and Authentication
- **SC-7:** Boundary Protection

##### 3. **Executive Order (EO) 14028**

Perintah Eksekutif Presiden AS untuk meningkatkan keamanan siber nasional. Dokumen ini memetakan bagaimana ZTA mendukung langkah-langkah yang diamanatkan dalam EO 14028.

#### 3.2 Metodologi Pemetaan

Dokumen mendefinisikan **tiga jenis hubungan** dalam pemetaan:

| Jenis Hubungan | Penjelasan | Contoh |
|---|---|---|
| **Supports** (Mendukung) | Fungsi ZTA dapat digunakan untuk mencapai kontrol keamanan tertentu | Policy Engine mendukung AC-3 (Access Enforcement) |
| **Is Supported By** (Didukung Oleh) | Kontrol keamanan diperlukan agar fungsi ZTA dapat berjalan | Multi-Factor Authentication (IA-2) mendukung Policy Engine |
| **No Relationship** | Tidak ada hubungan langsung | - |

---

### D. Komponen Arsitektur Logis ZTA

Dokumen merinci bagaimana komponen logis ZTA berikut membantu compliance:

#### 1. **Policy Engine (PE)**
- **Fungsi:** Pengambil keputusan akses
- **Tugas:** 
  - Mengevaluasi permintaan akses berdasarkan kebijakan
  - Mempertimbangkan konteks (identitas, perangkat, lokasi, waktu, tingkat ancaman)
  - Menghasilkan keputusan: izinkan atau tolak

#### 2. **Policy Administrator (PA)**
- **Fungsi:** Pelaksana keputusan akses
- **Tugas:**
  - Menerima keputusan dari Policy Engine
  - Mengkonfigurasi Policy Enforcement Point
  - Membuat atau menghentikan sesi komunikasi

#### 3. **Policy Enforcement Point (PEP)**
- **Fungsi:** Titik di mana akses diblokir atau diizinkan
- **Tugas:**
  - Meneruskan permintaan ke Policy Administrator
  - Mengizinkan atau memblokir akses resource berdasarkan instruksi dari PA
  - Memonitor sesi komunikasi

**Arsitektur Logis:**
```
User/Device → PEP → PA → PE (Keputusan) → PA → PEP → Resource
              ↑                                      ↓
              ←──────────────────────────────────────
```

---

## Poin-Poin Penting untuk Implementasi

### 1. Transisi dari Perimeter ke Identitas

> [!WARNING]
> Perubahan paradigma terbesar dalam ZTA adalah menghapus konsep **"jaringan terpercaya"** (trusted network).

**Sebelum ZTA:**
- Kepercayaan berdasarkan lokasi jaringan
- "Di dalam firewall = aman"
- Autentikasi sekali di awal

**Dengan ZTA:**
- Kepercayaan berdasarkan identitas yang terverifikasi
- Tidak ada perbedaan antara "dalam" dan "luar"
- Verifikasi berkelanjutan sepanjang sesi

### 2. Kepatuhan (Compliance)

**Manfaat ZTA untuk Compliance:**

✅ **Demonstrasi Kepatuhan yang Lebih Mudah**
- Pemetaan langsung ke framework yang sudah ada (CSF, SP 800-53, EO 14028)
- Dokumentasi yang terstruktur
- Audit trail yang komprehensif

✅ **Memenuhi Regulasi Modern**
- GDPR (privasi data)
- HIPAA (data kesehatan)
- PCI-DSS (data kartu kredit)
- Compliance lokal dan internasional lainnya

✅ **Prinsip Privacy by Design**
- Data minimization (meminimalkan data yang dikumpulkan)
- Access control yang ketat
- Enkripsi default

### 3. Mitigasi Risiko

**Strategi ZTA dalam Mengurangi Risiko:**

1. **Pengurangan Blast Radius**
   - Jika terjadi pembobolan, dampaknya terbatas
   - Segmentasi mikro membatasi lateral movement
   - Hak akses yang sangat terbatas

2. **Deteksi Lebih Cepat**
   - Monitoring real-time
   - Analitik perilaku pengguna (User Behavior Analytics)
   - Deteksi anomali

3. **Respons yang Lebih Cepat**
   - Kemampuan untuk segera mencabut akses
   - Isolasi otomatis saat terdeteksi ancaman
   - Forensik yang lebih baik melalui logging komprehensif

---

## Kesimpulan

### Mengapa Dokumen Ini Penting?

1. **Jembatan antara Teknologi dan Compliance**
   - Menghubungkan implementasi teknis ZTA dengan persyaratan bisnis dan regulasi
   
2. **Alat untuk Auditor dan Manajer Risiko**
   - Menyediakan pemetaan yang jelas dan terstruktur
   - Memudahkan proses audit dan assessment
   
3. **Panduan Praktis**
   - Bukan hanya teori, tetapi panduan implementasi nyata
   - Dapat digunakan sebagai checklist compliance

### Langkah Selanjutnya untuk Organisasi

1. **Pahami Volume Lainnya**
   - Volume A-D membahas aspek teknis implementasi
   - Volume E (ini) untuk aspek compliance dan risk management

2. **Lakukan Gap Analysis**
   - Bandingkan kondisi saat ini dengan requirement ZTA
   - Identifikasi area yang perlu improvement

3. **Buat Roadmap Implementasi**
   - Prioritaskan berdasarkan risiko dan compliance requirement
   - Implementasi bertahap (tidak perlu sekaligus)

4. **Dokumentasikan untuk Compliance**
   - Gunakan pemetaan dalam dokumen ini
   - Siapkan bukti untuk auditor

---

## Referensi dan Sumber Tambahan

Untuk informasi lebih lanjut tentang Zero Trust Architecture, silakan merujuk ke:

- **NIST SP 800-207:** Zero Trust Architecture (dokumen utama tentang ZTA)
- **NIST Cybersecurity Framework:** Framework keamanan siber komprehensif
- **NIST SP 800-53:** Security and Privacy Controls for Information Systems
- **Executive Order 14028:** Improving the Nation's Cybersecurity

---

## Glosarium Singkat

| Istilah | Penjelasan |
|---------|-----------|
| **ZTA** | Zero Trust Architecture - Arsitektur keamanan yang tidak memberikan kepercayaan implisit |
| **PEP** | Policy Enforcement Point - Titik dimana kebijakan akses ditegakkan |
| **PE** | Policy Engine - Mesin yang membuat keputusan akses |
| **PA** | Policy Administrator - Administrator yang mengeksekusi keputusan PE |
| **Least Privilege** | Prinsip memberikan hak akses minimum yang diperlukan |
| **Lateral Movement** | Pergerakan penyerang di dalam jaringan setelah akses awal |
| **Blast Radius** | Area dampak jika terjadi insiden keamanan |
| **Implicit Trust** | Kepercayaan otomatis tanpa verifikasi berkelanjutan |

---

**Catatan:** Dokumen ini adalah **Preliminary Draft** (draf awal), sehingga konten dapat berubah dalam versi final. Selalu merujuk ke versi terbaru dari publikasi NIST untuk informasi paling akurat.
