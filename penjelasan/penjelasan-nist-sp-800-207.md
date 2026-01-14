# Penjelasan NIST Special Publication 800-207: Zero Trust Architecture

## Informasi Dokumen

**Judul Lengkap:** NIST Special Publication 800-207 - Zero Trust Architecture

**Status:** Final (Publikasi Resmi)

**Tanggal Publikasi:** Agustus 2020

**Penulis:**
- Scott Rose (NIST)
- Oliver Borchert (NIST)
- Stu Mitchell (Stu20)
- Sean Connelly (Department of Homeland Security - DHS)

**Jumlah Halaman:** 59 halaman

**Kata Kunci:** Zero Trust, Zero Trust Architecture (ZTA), Cybersecurity, Network Security, Identity Management, Access Control

---

## Ringkasan Eksekutif

> [!IMPORTANT]
> Dokumen NIST SP 800-207 adalah **dokumen fundamental dan referensi utama** tentang Zero Trust Architecture. Ini adalah panduan resmi dari National Institute of Standards and Technology (NIST) yang mendefinisikan prinsip, arsitektur, dan implementasi Zero Trust.

**Zero Trust (ZT)** adalah paradigma keamanan siber yang berfokus pada perlindungan resource dengan premis bahwa kepercayaan **tidak pernah diberikan secara implisit**, tetapi harus **terus-menerus dievaluasi**.

**Zero Trust Architecture (ZTA)** adalah strategi end-to-end yang mencakup identitas, kredensial, manajemen identitas, operasi, endpoint, lingkungan hosting, dan infrastruktur yang menghubungkannya.

---

## Mengapa Zero Trust Diperlukan?

### Masalah dengan Model Keamanan Tradisional

Model keamanan **berbasis perimeter** (perimeter-based security) menghadapi kegagalan karena:

1. **Infrastruktur IT yang Kompleks**
   - Multi-cloud environments
   - Remote workers di berbagai lokasi
   - BYOD (Bring Your Own Device)
   - Partner dan vendor eksternal yang perlu akses

2. **Asumsi "Trusted Network" yang Salah**
   ```
   Luar Firewall = Tidak Aman ❌
   Dalam Firewall = Aman ✅
   ```
   **Realita:** Ancaman bisa datang dari dalam!

3. **Lateral Movement**
   - Setelah penyerang masuk, mereka bisa bergerak bebas
   - Satu titik kompromi = seluruh jaringan terancam

---

## Definisi Kunci

### 1. Zero Trust (ZT)
Kumpulan konsep dan ide yang dirancang untuk **meminimalkan ketidakpastian** dalam menegakkan keputusan akses yang akurat dengan **hak istimewa paling sedikit (least privilege)** per-permintaan.

### 2. Zero Trust Architecture (ZTA)
Rencana keamanan siber perusahaan yang **menggunakan konsep-konsep zero trust** dan mencakup hubungan komponen, perencanaan alur kerja, dan kebijakan akses.

### 3. Zero Trust Enterprise (ZTE)
Infrastruktur jaringan fisik dan virtual serta **kebijakan operasional** untuk sebuah perusahaan yang menerapkan ZTA.

---

## Tujuh Prinsip Dasar Zero Trust (The 7 Tenets)

> [!NOTE]
> Ini adalah fondasi dari semua implementasi Zero Trust. Ketujuh prinsip ini HARUS dipenuhi untuk mencapai ZTA yang benar.

### 1️⃣ Semua Sumber Data dan Layanan Komputasi Dianggap sebagai Resource
- Tidak peduli di mana lokasinya (on-premise, cloud, edge)
- Semua harus dilindungi dengan cara yang sama

### 2️⃣ Semua Komunikasi Diamankan Terlepas dari Lokasi Jaringan
- Enkripsi default untuk semua komunikasi
- Tidak ada perbedaan antara "dalam" dan "luar" jaringan
- Tidak ada zona "terpercaya" berdasarkan lokasi

### 3️⃣ Akses ke Resource Perusahaan Diberikan per-Sesi
- Setiap sesi baru memerlukan otorisasi ulang
- Tidak ada "remember me" atau sesi yang bertahan lama tanpa verifikasi
- Least privilege access: hanya akses yang diperlukan untuk sesi tersebut

### 4️⃣ Akses Ditentukan oleh Kebijakan Dinamis
Kebijakan mempertimbangkan banyak faktor:
- **Identitas klien** (siapa yang meminta?)
- **Aplikasi/layanan** (apa yang diminta?)
- **Status keamanan aset** (device health, patch level)
- **Atribut perilaku dan lingkungan** (lokasi, waktu, pola akses)

### 5️⃣ Perusahaan Memonitor dan Mengukur Integritas Semua Aset
- Continuous monitoring untuk semua device
- Security posture assessment berkelanjutan
- Termasuk aset yang dimiliki dan aset yang terkait (partner, BYOD)

### 6️⃣ Autentikasi dan Otorisasi Resource Bersifat Dinamis dan Ketat
- Verifikasi sebelum akses diberikan
- Re-authentication dan re-authorization berkala
- Strictly enforced: tidak ada pengecualian

### 7️⃣ Perusahaan Mengumpulkan Informasi Sebanyak Mungkin tentang Status Aset dan Infrastruktur
- Data analytics untuk meningkatkan security posture
- Pembelajaran dari pola akses
- Deteksi anomali dan ancaman

---

## Komponen Logis Zero Trust Architecture

### Arsitektur Overview

```
┌─────────────┐
│   Subject   │ (User, Service, Device)
│  (Pemohon)  │
└──────┬──────┘
       │
       ▼
┌─────────────────────────────────────────┐
│  Policy Enforcement Point (PEP)         │ ◄── Gateway/Proxy
│  • Intercepts requests                  │
│  • Monitors connections                 │
│  • Enables/Terminates sessions          │
└──────┬──────────────────────────────────┘
       │
       │ ◄──── Control Plane ────►
       │
       ▼
┌─────────────────────────────────────────┐
│  Policy Decision Point (PDP)            │
│  ┌────────────────────────────────────┐ │
│  │ Policy Engine (PE)                 │ │
│  │ • Makes access decisions           │ │
│  │ • Evaluates policies               │ │
│  │ • Checks trust score               │ │
│  └────────────────────────────────────┘ │
│  ┌────────────────────────────────────┐ │
│  │ Policy Administrator (PA)          │ │
│  │ • Executes PE decisions            │ │
│  │ • Opens/closes communication path  │ │
│  │ • Configures PEP                   │ │
│  └────────────────────────────────────┘ │
└─────────────────────────────────────────┘
       │
       ▼ ◄──── Data Plane ────►
┌─────────────┐
│  Resource   │ (Application, Data, Service)
└─────────────┘
```

### 1. Policy Enforcement Point (PEP)

**Fungsi:**
- Gerbang utama untuk semua akses resource
- Intercepts (menangkap) semua permintaan akses
- Meneruskan permintaan ke Policy Administrator
- Memonitor dan mengontrol sesi komunikasi

**Karakteristik:**
- Dapat berupa gateway, proxy, atau agent di device
- Memutus atau mengizinkan koneksi berdasarkan instruksi PA
- Berfungsi sebagai "penjaga pintu" (gatekeeper)

### 2. Policy Engine (PE)

**Fungsi:**
- **Otak dari sistem** - membuat keputusan akses
- Mengevaluasi permintaan berdasarkan kebijakan
- Menghitung "trust score" atau tingkat kepercayaan

**Input yang Dipertimbangkan:**
- Data dari CDM (Continuous Diagnostics and Mitigation) system
- Threat intelligence feeds
- Activity logs
- Data Akses Resource (apa yang diminta?)
- Data Subjek (siapa yang meminta?)
- Historical behavior patterns

**Output:**
- **Grant** (izinkan)
- **Deny** (tolak)
- **Conditional** (izinkan dengan batasan tertentu)

### 3. Policy Administrator (PA)

**Fungsi:**
- **Eksekutor** keputusan dari Policy Engine
- Mengkonfigurasi PEP untuk membuka atau menutup jalur komunikasi
- Membuat session-specific credentials atau tokens

**Proses:**
1. Terima keputusan dari PE
2. Generate authentication token atau credential
3. Kirim instruksi ke PEP
4. Monitor sesi yang aktif

### 4. Control Plane vs Data Plane

| Aspek | Control Plane | Data Plane |
|-------|---------------|------------|
| **Fungsi** | Manajemen dan decision-making | Aliran data aplikasi aktual |
| **Komunikasi** | PDP ↔ PEP | Subject ↔ Resource |
| **Konten** | Policy, commands, authentication | Application data, business logic |
| **Keamanan** | Highly secured, encrypted | Secured per ZT principles |

---

## Model Deployment ZTA

### Model 1: Device Agent/Gateway-Based

```
Device (with Agent) → Gateway → Policy Engine → Resource
```

**Karakteristik:**
- Agent software di setiap device
- Gateway sebagai PEP pusat
- Cocok untuk enterprise dengan kontrol device yang kuat

**Kelebihan:**
- ✅ Device posture dapat dimonitor secara detail
- ✅ Better control atas endpoint

**Kekurangan:**
- ❌ Memerlukan instalasi agent di semua device
- ❌ Tidak cocok untuk BYOD tanpa manajemen

### Model 2: Enclave-Based (Network Segmentation)

```
Segmented Networks → Gateways antar Enclave → Micro-perimeters
```

**Karakteristik:**
- Network dibagi menjadi enclave-enclave kecil
- Setiap enclave memiliki PEP sendiri
- Micro-segmentation untuk isolasi

**Kelebihan:**
- ✅ Mengurangi blast radius
- ✅ Dapat diimplementasi bertahap

**Kekurangan:**
- ❌ Kompleksitas manajemen meningkat
- ❌ Memerlukan perubahan arsitektur jaringan

### Model 3: Resource Portal

```
User → Web Portal (PEP) → Backend Resources
```

**Karakteristik:**
- Portal tunggal untuk akses semua resource
- Reverse proxy atau API gateway
- Web-based access

**Kelebihan:**
- ✅ User experience yang konsisten
- ✅ Tidak perlu agent di client
- ✅ Cocok untuk web applications

**Kekurangan:**
- ❌ Terbatas pada protokol yang didukung portal
- ❌ Single point of failure jika tidak di-redundansi

### Model 4: Device Application Sandboxing

```
Isolated App Containers → Per-app Network Controls
```

**Karakteristik:**
- Setiap aplikasi berjalan di sandbox
- Network controls per aplikasi
- Containerization atau virtualization

**Kelebihan:**
- ✅ Isolasi yang sangat kuat
- ✅ Cocok untuk high-security environments

**Kekurangan:**
- ❌ Overhead performance
- ❌ Kompleksitas development

---

## Skenario Deployment (Use Cases)

### 1. Enterprise dengan Remote Workers

**Konteks:**
- Karyawan bekerja dari rumah, kafe, atau lokasi remote lainnya
- Menggunakan berbagai device dan koneksi internet

**Implementasi ZTA:**
```
Remote Worker → VPN/ZTNA Gateway (PEP) → Policy Engine → Corporate Resources
```

**Keuntungan:**
- Tidak perlu membedakan "dalam" vs "luar" kantor
- Akses yang sama ketatnya dari mana pun
- Device health checking sebelum akses diberikan

### 2. Multi-Cloud dan Cloud-to-Cloud

**Konteks:**
- Aplikasi tersebar di AWS, Azure, GCP
- Microservices berkomunikasi antar cloud

**Implementasi ZTA:**
```
Service A (AWS) → API Gateway (PEP) → Policy Engine → Service B (Azure)
```

**Keuntungan:**
- Enkripsi dan autentikasi untuk semua komunikasi inter-cloud
- Tidak bergantung pada network perimeter cloud provider
- Centralized policy management

### 3. Kerjasama dengan Kontraktor dan Partner

**Konteks:**
- Partner eksternal perlu akses terbatas ke resource tertentu
- Kontractor sementara dengan akses yang berubah-ubah

**Implementasi ZTA:**
```
Partner User → Portal (PEP) → Policy Engine (dengan rules khusus) → Limited Resources
```

**Keuntungan:**
- Least privilege: akses hanya ke resource yang diperlukan
- Time-bound access yang otomatis expired
- Audit trail yang jelas

### 4. Kolaborasi Lintas Organisasi

**Konteks:**
- Berbagi data antar organisasi (B2B)
- Joint projects dengan multiple stakeholders

**Implementasi ZTA:**
```
Org A User → Federation Gateway → Policy Engine → Org B Resources
```

**Keuntungan:**
- Identity federation tanpa share credentials
- Fine-grained access control
- Compliance dengan regulasi data sharing

---

## Model Ancaman (Threat Model)

> [!CAUTION]
> Zero Trust bukan silver bullet. Ada ancaman-ancaman spesifik yang perlu diwaspadai dalam implementasi ZTA.

### 1. Subversion of ZTA Decision Process

**Ancaman:**
- Policy Engine atau Policy Administrator dikompromikan
- Attacker memanipulasi keputusan akses

**Mitigasi:**
- ✅ Hardening komponen PDP dengan security terbaik
- ✅ Multi-factor authentication untuk admin
- ✅ Audit logging yang komprehensif
- ✅ Monitoring anomali di decision logs

### 2. Denial-of-Service (DoS) terhadap ZTA Components

**Ancaman:**
- Serangan DoS ke Policy Engine atau PEP
- Membuat akses legitimate menjadi tidak tersedia

**Mitigasi:**
- ✅ Redundansi dan high availability
- ✅ Rate limiting dan traffic filtering
- ✅ Failover mechanisms
- ✅ DDoS protection services

### 3. Stolen Credentials atau Insider Threats

**Ancaman:**
- Kredensial yang valid dicuri (phishing, malware)
- Insider yang authorized bertindak jahat

**Mitigasi:**
- ✅ Multi-factor authentication (MFA) wajib
- ✅ Behavioral analytics (UEBA - User and Entity Behavior Analytics)
- ✅ Continuous verification
- ✅ Anomaly detection

### 4. Ancaman Tersembunyi dalam Enkripsi

**Ancaman:**
- Malware atau command-and-control traffic disembunyikan dalam encrypted traffic
- PEP tidak bisa inspect encrypted payload

**Mitigasi:**
- ✅ TLS inspection (dengan perhatian pada privacy)
- ✅ Endpoint detection and response (EDR)
- ✅ Network behavior analysis
- ✅ Certificate pinning

### 5. Kerentanan dalam Storage Data Keputusan

**Ancaman:**
- Database yang menyimpan logs, policies, atau user data dikompromikan
- Information leakage

**Mitigasi:**
- ✅ Enkripsi at rest untuk semua data
- ✅ Access control ketat untuk database
- ✅ Regular security audits
- ✅ Data retention policies

---

## Panduan Migrasi ke Zero Trust Architecture

> [!TIP]
> Migrasi ke ZTA adalah perjalanan, bukan destinasi. Jangan coba implementasi semuanya sekaligus!

### Langkah 1: Identifikasi Actors (Subjects)

**Apa yang Harus Dilakukan:**
- Inventory semua users (employees, contractors, partners)
- Inventory semua devices (laptops, phones, IoT)
- Inventory semua services dan aplikasi

**Output:**
- Daftar lengkap semua entitas yang akan mengakses resource
- Kategorisasi berdasarkan role dan trust level

### Langkah 2: Identifikasi Assets dan Processes

**Apa yang Harus Dilakukan:**
- Katalog semua asset (aplikasi, data, services)
- Map data flows antar sistem
- Identifikasi dependencies

**Output:**
- Asset inventory dengan classification (public, internal, confidential, restricted)
- Process flow diagrams
- Data flow diagrams

### Langkah 3: Mapping dan Observasi Data Flows

**Apa yang Harus Dilakukan:**
- Monitor traffic patterns
- Identifikasi komunikasi normal vs anomali
- Dokumentasikan protokol dan ports yang digunakan

**Output:**
- Network traffic baselines
- Communication patterns
- Dependency maps

### Langkah 4: Formulasi Kebijakan ZT untuk "Candidate Processes"

**Apa yang Harus Dilakukan:**
- Pilih process atau aplikasi untuk pilot ZT
- Buat access policies berdasarkan least privilege
- Define context-aware rules

**Kriteria Candidate yang Baik:**
- ✅ High-value atau high-risk resources
- ✅ Well-documented processes
- ✅ Manageable scope untuk pilot

**Output:**
- Written policies untuk candidate processes
- Risk assessment
- Success criteria

### Langkah 5: Identifikasi Solusi Kandidat

**Apa yang Harus Dilakukan:**
- Evaluasi vendor dan teknologi ZTA
- Assess compatibility dengan infrastruktur existing
- Proof of Concept (PoC) untuk solusi terpilih

**Pertimbangan:**
- Apakah mendukung existing identity provider?
- Apakah bisa integrate dengan SIEM dan monitoring tools?
- Scalability dan performance
- Total Cost of Ownership (TCO)

### Langkah 6: Initial Deployment dan Monitoring

**Apa yang Harus Dilakukan:**
- Deploy ZTA untuk candidate processes
- Monitor secara intensif
- Collect feedback dari users

**Metrik yang Diukur:**
- Access request latency
- User experience (UX) impact
- False positives/negatives dalam policy engine
- Security incidents

**Mode Deployment:**
```
Shadow Mode → Log Only → Enforce with Exceptions → Full Enforcement
```

### Langkah 7: Ekspansi ZTA

**Apa yang Harus Dilakukan:**
- Evaluate kesuksesan pilot
- Expand ke more processes dan resources
- Iterasi dan improve policies

**Strategi Ekspansi:**
- ✅ Prioritaskan based on risk dan business value
- ✅ Bertahap, jangan semuanya sekaligus
- ✅ Lessons learned dari pilot

---

## Keterkaitan dengan Panduan Federal AS Lainnya

### 1. TIC 3.0 (Trusted Internet Connections)

**Apa itu TIC:**
- Program untuk konsolidasi dan mengamankan external network connections federal agencies

**Hubungan dengan ZTA:**
- TIC 3.0 menerima ZTA sebagai pendekatan yang valid
- PEP dalam ZTA dapat berfungsi sebagai TIC access point
- Compliance dengan TIC dapat dicapai melalui ZTA

### 2. CDM (Continuous Diagnostics and Mitigation)

**Apa itu CDM:**
- Program untuk improve cybersecurity posture melalui better visibility

**Hubungan dengan ZTA:**
- CDM menyediakan data untuk Policy Engine
- Asset discovery dan inventory dari CDM → input untuk ZTA
- Vulnerability management dari CDM → trust scoring dalam ZTA

### 3. FICAM (Federal Identity, Credential, and Access Management)

**Apa itu FICAM:**
- Framework untuk identity management di federal agencies

**Hubungan dengan ZTA:**
- FICAM principles align dengan ZTA principles
- Identity management adalah foundational untuk ZTA
- PIV cards dan strong authentication = critical untuk ZTA

---

## Perbandingan: Perimeter-Based vs Zero Trust

| Aspek | Perimeter-Based Security | Zero Trust Architecture |
|-------|--------------------------|-------------------------|
| **Filosofi** | "Trust but verify" | "Never trust, always verify" |
| **Zona Kepercayaan** | Inside = Trusted, Outside = Untrusted | No trusted zones |
| **Autentikasi** | Sekali di perimeter | Continuous, per-session |
| **Akses** | Broad access setelah autentikasi | Least privilege, per-resource |
| **Asumsi** | Network location = security | Assume breach |
| **Segmentasi** | Coarse-grained (DMZ, Internal) | Micro-segmentation |
| **Monitoring** | Perimeter traffic | All traffic, all the time |
| **Enkripsi** | VPN untuk remote access | End-to-end, always |

---

## Kesimpulan dan Rekomendasi

### Kesimpulan Utama

1. **Zero Trust adalah Paradigm Shift**
   - Bukan produk yang dibeli, tetapi arsitektur yang dibangun
   - Memerlukan perubahan kultur dan mindset organisasi

2. **Implementasi Bertahap**
   - Jangan coba "big bang" implementation
   - Start small, prove value, expand

3. **People, Process, Technology**
   - Teknologi saja tidak cukup
   - Perlu policy yang jelas dan user awareness

### Manfaat Implementasi ZTA

✅ **Keamanan yang Lebih Baik**
- Reduced attack surface
- Limited blast radius
- Better threat detection

✅ **Fleksibilitas dan Agilitas**
- Support remote work dan mobile
- Cloud-ready architecture
- Easier onboarding untuk partner

✅ **Compliance**
- Better audit trails
- Data protection yang lebih baik
- Alignment dengan regulatory requirements

✅ **Visibilitas**
- Comprehensive logging
- Better incident response
- Data-driven security decisions

### Next Steps untuk Organisasi

1. **Educate dan Socialize**
   - Train security team tentang ZT principles
   - Executive buy-in
   - User awareness

2. **Assess Current State**
   - Inventory assets dan data flows
   - Gap analysis vs ZT principles
   - Risk assessment

3. **Define Target State**
   - Pilih deployment model yang sesuai
   - Define policies dan governance
   - Set timeline dan milestones

4. **Pilot dan Iterate**
   - Start dengan high-value use case
   - Measure dan learn
   - Expand gradually

---

## Referensi dan Bacaan Lebih Lanjut

### Dokumen NIST Terkait

- **NIST SP 800-53:** Security and Privacy Controls
- **NIST SP 1800-35 (Volume A-E):** Implementing a Zero Trust Architecture (panduan praktis)
- **NIST Cybersecurity Framework (CSF):** Framework keamanan komprehensif
- **NIST SP 800-63:** Digital Identity Guidelines

### Konsep Terkait

- **Software-Defined Perimeter (SDP)**
- **Identity and Access Management (IAM)**
- **Privileged Access Management (PAM)**
- **Security Information and Event Management (SIEM)**
- **User and Entity Behavior Analytics (UEBA)**

---

## Glosarium

| Istilah | Penjelasan |
|---------|-----------|
| **ZT** | Zero Trust - Paradigma keamanan tanpa kepercayaan implisit |
| **ZTA** | Zero Trust Architecture - Implementasi arsitektur zero trust |
| **ZTE** | Zero Trust Enterprise - Organisasi yang menerapkan ZTA |
| **PEP** | Policy Enforcement Point - Titik penegakan kebijakan |
| **PE** | Policy Engine - Mesin pembuat keputusan akses |
| **PA** | Policy Administrator - Administrator yang mengeksekusi keputusan PE |
| **PDP** | Policy Decision Point - Gabungan PE dan PA |
| **Least Privilege** | Prinsip memberikan hak akses minimum |
| **Micro-segmentation** | Pembagian jaringan menjadi zona-zona kecil |
| **Lateral Movement** | Pergerakan attacker di dalam jaringan |
| **Implicit Trust** | Kepercayaan otomatis tanpa verifikasi |
| **Trust Score** | Skor tingkat kepercayaan untuk subject atau resource |
| **CDM** | Continuous Diagnostics and Mitigation |
| **TIC** | Trusted Internet Connections |
| **FICAM** | Federal Identity, Credential, and Access Management |

---

**Catatan Penting:**

> [!WARNING]
> Zero Trust Architecture memerlukan komitmen jangka panjang. Ini bukan solusi instan dan memerlukan iterasi berkelanjutan untuk kesuksesan penuh.

**Dokumen ini berdasarkan:** NIST Special Publication 800-207 (Agustus 2020)

**Untuk informasi terbaru, selalu rujuk ke:** https://csrc.nist.gov/publications/detail/sp/800-207/final
