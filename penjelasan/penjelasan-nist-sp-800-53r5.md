# Penjelasan NIST Special Publication 800-53 Revision 5: Security and Privacy Controls

## Informasi Dokumen

**Judul Lengkap:** NIST Special Publication 800-53 Revision 5 - Security and Privacy Controls for Information Systems and Organizations

**Status:** Final (Publikasi Resmi)

**Tanggal Publikasi:** September 2020 (dengan pembaruan Desember 2020)

**Jumlah Halaman:** 492 halaman

**Kata Kunci:** Security Controls, Privacy Controls, Risk Management Framework (RMF), Control Baselines, Cybersecurity, Information Security, Privacy Protection

---

## Ringkasan Eksekutif

> [!IMPORTANT]
> NIST SP 800-53r5 adalah **katalog komprehensif** dari kontrol keamanan dan privasi yang dapat digunakan oleh organisasi untuk melindungi sistem informasi dan data. Ini merupakan dokumen fundamental untuk implementasi Risk Management Framework (RMF).

**Perubahan Signifikan di Revision 5:**
- **Integrasi Privasi:** Kontrol privasi tidak lagi di lampiran terpisah, tetapi terintegrasi penuh dalam katalog utama
- **Pemisahan Baseline:** Security baselines (Low, Moderate, High) dipindahkan ke dokumen terpisah (NIST SP 800-53B)
- **Keluarga Kontrol Baru:** Penambahan kontrol untuk Supply Chain Risk Management (SR) dan PII Processing (PT)
- **Outcome-Based:** Lebih fokus pada hasil yang dicapai daripada implementasi spesifik

---

## Tujuan dan Ruang Lingkup

### Tujuan Dokumen

1. **Menyediakan Katalog Kontrol**
   - Daftar lengkap kontrol keamanan dan privasi
   - Dapat diterapkan pada berbagai jenis sistem dan organisasi

2. **Mendukung Risk Management Framework**
   - Bagian integral dari NIST RMF
   - Membantu organisasi mengelola risiko keamanan dan privasi

3. **Fleksibilitas dan Customization**
   - Kontrol dapat disesuaikan (tailored) dengan kebutuhan spesifik
   - Mendukung berbagai deployment scenarios

### Target Audiens

- **Chief Information Security Officers (CISOs)**
- **Privacy Officers**
- **Risk Managers**
- **System Owners dan Administrators**
- **Auditor dan Assessor**
- **Procurement Officers**

---

## Struktur Dokumen

Dokumen NIST SP 800-53r5 terbagi dalam tiga chapter utama dan beberapa appendix:

### Chapter 1: Introduction (Pendahuluan)

**Isi:**
- Latar belakang dan tujuan
- Hubungan dengan Risk Management Framework
- Audiens dan scope
- Organisasi dokumen

### Chapter 2: The Fundamentals (Dasar-Dasar)

**Isi:**
- Struktur dan organisasi kontrol
- Integrasi keamanan dan privasi
- Control selection dan tailoring process
- Implementation dalam RMF
- Assessment dan monitoring

**Konsep Penting:**
- **Control Families:** Pengelompokan kontrol berdasarkan fungsi
- **Control Baselines:** Set kontrol untuk impact levels berbeda
- **Control Tailoring:** Penyesuaian kontrol dengan konteks organisasi
- **Overlays:** Kumpulan kontrol tambahan untuk use case spesifik

### Chapter 3: The Controls (Katalog Kontrol)

**Isi:**
- **Katalog lengkap 20 keluarga kontrol**
- Setiap kontrol berisi:
  - **Control Identifier:** Kode unik (contoh: AC-2)
  - **Control Name:** Nama kontrol
  - **Control Statement:** Persyaratan kontrol
  - **Discussion:** Penjelasan detail
  - **Related Controls:** Kontrol yang terkait
  - **Control Enhancements:** Peningkatan opsional untuk kontrol dasar
  - **References:** Dokumen terkait

### Appendices

- **Appendix A:** References (Referensi)
- **Appendix B:** Glossary (Glosarium)
- **Appendix C:** Acronyms (Akronim)
- **Appendix D:** Summary of Controls (Ringkasan Kontrol)

---

## 20 Keluarga Kontrol (Control Families)

> [!NOTE]
> Setiap keluarga kontrol memiliki identifier dua huruf dan mencakup area keamanan/privasi spesifik.

### 1. AC - Access Control (Kontrol Akses)

**Fokus:** Pembatasan akses ke sistem informasi dan data

**Kontrol Utama:**
- **AC-1:** Policy and Procedures
- **AC-2:** Account Management
- **AC-3:** Access Enforcement
- **AC-4:** Information Flow Enforcement
- **AC-6:** Least Privilege
- **AC-7:** Unsuccessful Logon Attempts
- **AC-17:** Remote Access
- **AC-20:** Use of External Systems

**Contoh Implementasi:**
```
AC-2: Account Management
→ Organisasi harus:
  • Mengidentifikasi dan memilih jenis akun yang diizinkan
  • Menetapkan account managers
  • Mereview akun secara berkala
  • Menonaktifkan akun yang tidak aktif
```

### 2. AT - Awareness and Training (Kesadaran dan Pelatihan)

**Fokus:** Pendidikan keamanan dan privasi untuk personel

**Kontrol Utama:**
- **AT-1:** Policy and Procedures
- **AT-2:** Literacy Training and Awareness
- **AT-3:** Role-Based Training
- **AT-4:** Training Records

### 3. AU - Audit and Accountability (Audit dan Akuntabilitas)

**Fokus:** Logging, monitoring, dan audit trail

**Kontrol Utama:**
- **AU-2:** Event Logging
- **AU-3:** Content of Audit Records
- **AU-6:** Audit Record Review, Analysis, and Reporting
- **AU-9:** Protection of Audit Information
- **AU-12:** Audit Record Generation

**Pentingnya:**
- ✅ Deteksi insiden keamanan
- ✅ Forensik dan investigasi
- ✅ Compliance dan accountability
- ✅ Analisis tren dan anomali

### 4. CA - Assessment, Authorization, and Monitoring

**Fokus:** Evaluasi kontrol keamanan dan otorisasi sistem

**Kontrol Utama:**
- **CA-1:** Policy and Procedures
- **CA-2:** Control Assessments
- **CA-3:** Information Exchange
- **CA-5:** Plan of Action and Milestones
- **CA-6:** Authorization
- **CA-7:** Continuous Monitoring
- **CA-8:** Penetration Testing
- **CA-9:** Internal System Connections

### 5. CM - Configuration Management (Manajemen Konfigurasi)

**Fokus:** Baseline dan kontrol perubahan sistem

**Kontrol Utama:**
- **CM-2:** Baseline Configuration
- **CM-3:** Configuration Change Control
- **CM-4:** Impact Analysis
- **CM-6:** Configuration Settings
- **CM-7:** Least Functionality
- **CM-8:** System Component Inventory

### 6. CP - Contingency Planning (Perencanaan Kontingensi)

**Fokus:** Business continuity dan disaster recovery

**Kontrol Utama:**
- **CP-2:** Contingency Plan
- **CP-3:** Contingency Training
- **CP-4:** Plan Testing
- **CP-6:** Alternate Storage Site
- **CP-7:** Alternate Processing Site
- **CP-9:** System Backup
- **CP-10:** System Recovery and Reconstitution

### 7. IA - Identification and Authentication

**Fokus:** Verifikasi identitas pengguna dan perangkat

**Kontrol Utama:**
- **IA-2:** Identification and Authentication (Organizational Users)
- **IA-3:** Device Identification and Authentication
- **IA-4:** Identifier Management
- **IA-5:** Authenticator Management
- **IA-8:** Identification and Authentication (Non-Organizational Users)

**Contoh Enhancement:**
```
IA-2(1): Multi-Factor Authentication
→ Memerlukan setidaknya dua faktor berbeda:
  • Something you know (password)
  • Something you have (token, phone)
  • Something you are (biometrics)
```

### 8. IR - Incident Response (Respons Insiden)

**Fokus:** Deteksi, respons, dan pemulihan dari insiden keamanan

**Kontrol Utama:**
- **IR-1:** Policy and Procedures
- **IR-2:** Incident Response Training
- **IR-4:** Incident Handling
- **IR-5:** Incident Monitoring
- **IR-6:** Incident Reporting
- **IR-7:** Incident Response Assistance
- **IR-8:** Incident Response Plan

### 9. MA - Maintenance (Pemeliharaan)

**Fokus:** Pemeliharaan sistem yang aman

**Kontrol Utama:**
- **MA-2:** Controlled Maintenance
- **MA-3:** Maintenance Tools
- **MA-4:** Nonlocal Maintenance
- **MA-5:** Maintenance Personnel
- **MA-6:** Timely Maintenance

### 10. MP - Media Protection (Perlindungan Media)

**Fokus:** Proteksi media fisik dan digital

**Kontrol Utama:**
- **MP-2:** Media Access
- **MP-3:** Media Marking
- **MP-4:** Media Storage
- **MP-5:** Media Transport
- **MP-6:** Media Sanitization
- **MP-7:** Media Use

### 11. PE - Physical and Environmental Protection

**Fokus:** Keamanan fisik fasilitas dan infrastruktur

**Kontrol Utama:**
- **PE-2:** Physical Access Authorizations
- **PE-3:** Physical Access Control
- **PE-6:** Monitoring Physical Access
- **PE-8:** Visitor Access Records
- **PE-13:** Fire Protection
- **PE-14:** Environmental Controls (temperature, humidity)
- **PE-15:** Water Damage Protection

### 12. PL - Planning (Perencanaan)

**Fokus:** Perencanaan keamanan dan privasi sistem

**Kontrol Utama:**
- **PL-2:** System Security and Privacy Plans
- **PL-4:** Rules of Behavior
- **PL-7:** Concept of Operations
- **PL-8:** Security and Privacy Architectures
- **PL-10:** Baseline Selection

### 13. PM - Program Management (Manajemen Program)

**Fokus:** Governance dan manajemen program keamanan

**Kontrol Utama:**
- **PM-1:** Information Security Program Plan
- **PM-2:** Information Security Program Leadership
- **PM-9:** Risk Management Strategy
- **PM-15:** Security and Privacy Groups and Associations
- **PM-16:** Threat Awareness Program

> [!NOTE]
> PM controls bersifat **program-level** (organisasi), bukan system-specific.

### 14. PS - Personnel Security (Keamanan Personel)

**Fokus:** Screening, training, dan terminasi personel

**Kontrol Utama:**
- **PS-3:** Personnel Screening
- **PS-4:** Personnel Termination
- **PS-5:** Personnel Transfer
- **PS-6:** Access Agreements
- **PS-7:** External Personnel Security
- **PS-8:** Personnel Sanctions

### 15. PT - PII Processing and Transparency

**Fokus:** Pemrosesan Personally Identifiable Information (PII)

> [!IMPORTANT]
> PT adalah keluarga kontrol **baru di Revision 5** yang fokus pada privasi.

**Kontrol Utama:**
- **PT-1:** Policy and Procedures
- **PT-2:** Authority to Process PII
- **PT-3:** PII Processing Purposes
- **PT-4:** Consent
- **PT-5:** Privacy Notice
- **PT-6:** System of Records Notice
- **PT-7:** Specific Categories of PII
- **PT-8:** Computer Matching Requirements

**Prinsip Privacy:**
- Data minimization
- Purpose specification
- Transparency
- Individual participation
- Data quality and integrity

### 16. RA - Risk Assessment (Penilaian Risiko)

**Fokus:** Identifikasi dan evaluasi risiko

**Kontrol Utama:**
- **RA-1:** Policy and Procedures
- **RA-2:** Security Categorization
- **RA-3:** Risk Assessment
- **RA-5:** Vulnerability Monitoring and Scanning
- **RA-7:** Risk Response
- **RA-9:** Criticality Analysis
- **RA-10:** Threat Hunting

### 17. SA - System and Services Acquisition

**Fokus:** Lifecycle keamanan dalam pengadaan sistem

**Kontrol Utama:**
- **SA-3:** System Development Life Cycle
- **SA-4:** Acquisition Process
- **SA-8:** Security and Privacy Engineering Principles
- **SA-9:** External System Services
- **SA-10:** Developer Configuration Management
- **SA-11:** Developer Testing and Evaluation
- **SA-15:** Development Process, Standards, and Tools
- **SA-22:** Unsupported System Components

### 18. SC - System and Communications Protection

**Fokus:** Boundary protection, enkripsi, dan network security

**Kontrol Utama:**
- **SC-7:** Boundary Protection
- **SC-8:** Transmission Confidentiality and Integrity
- **SC-12:** Cryptographic Key Establishment and Management
- **SC-13:** Cryptographic Protection
- **SC-20:** Secure Name/Address Resolution (DNS)
- **SC-23:** Session Authenticity
- **SC-28:** Protection of Information at Rest

**Contoh:**
```
SC-8: Transmission Confidentiality and Integrity
→ Melindungi kerahasiaan DAN integritas informasi yang ditransmisikan
→ Implementasi: TLS, IPsec, VPN
```

### 19. SI - System and Information Integrity

**Fokus:** Proteksi dari malware dan monitoring integritas

**Kontrol Utama:**
- **SI-2:** Flaw Remediation (patching)
- **SI-3:** Malicious Code Protection
- **SI-4:** System Monitoring
- **SI-5:** Security Alerts, Advisories, and Directives
- **SI-7:** Software, Firmware, and Information Integrity
- **SI-10:** Information Input Validation
- **SI-12:** Information Management and Retention

### 20. SR - Supply Chain Risk Management

**Fokus:** Keamanan supply chain dan komponen sistem

> [!IMPORTANT]
> SR adalah keluarga kontrol **baru di Revision 5** yang sangat penting di era global supply chain.

**Kontrol Utama:**
- **SR-1:** Policy and Procedures
- **SR-2:** Supply Chain Risk Management Plan
- **SR-3:** Supply Chain Controls and Processes
- **SR-4:** Provenance (asal-usul komponen)
- **SR-5:** Acquisition Strategies, Tools, and Methods
- **SR-6:** Supplier Assessments and Reviews
- **SR-8:** Notification Agreements
- **SR-11:** Component Authenticity

**Mengapa Penting:**
- Ancaman dari komponen yang disusupi (compromised)
- Counterfeit hardware/software
- Dependency pada vendor asing
- Third-party risk management

---

## Struktur Kontrol

Setiap kontrol dalam katalog mengikuti format standar:

### Format Kontrol

```markdown
## AC-2 ACCOUNT MANAGEMENT

Control:
[Pernyataan kontrol - apa yang harus dilakukan]

Discussion:
[Penjelasan detail tentang kontrol, contoh implementasi, konsiderasi]

Related Controls:
[Daftar kontrol lain yang terkait]

Control Enhancements:
[Peningkatan opsional untuk memperkuat kontrol dasar]

References:
[Standar dan dokumen terkait]
```

### Contoh Lengkap: AC-3 Access Enforcement

**Control Statement:**
> Organisasi harus menegakkan (enforce) otorisasi yang telah disetujui untuk akses logis ke informasi dan sumber daya sistem sesuai dengan kebijakan kontrol akses yang berlaku.

**Discussion:**
Access enforcement mechanisms menggunakan access control policies (misalnya identity-based, role-based, attribute-based) untuk mengontrol akses antara users atau processes dan objek dalam sistem. Access enforcement meliputi:
- Verification of access authorizations
- Mediation of all access attempts
- Application of policy constraints

**Related Controls:**
- AC-2 (Account Management)
- AC-4 (Information Flow Enforcement)
- AC-5 (Separation of Duties)
- AC-6 (Least Privilege)
- AU-2 (Event Logging)
- IA-2 (Identification and Authentication)
- SA-8 (Security Engineering Principles)
- SC-2 (Separation of System and User Functionality)

**Control Enhancements:**

**(1) AC-3(1): Restricted Access to Privileged Functions**
- Membatasi akses ke fungsi privileged (security-relevant)
- Deployment: RBAC dengan strict approval untuk admin roles

**(2) AC-3(2): Dual Authorization**
- Memerlukan dua atau lebih individu untuk authorize tindakan tertentu
- Use case: Financial transactions, system-critical changes

**(3) AC-3(3): Mandatory Access Control**
- Enforce MAC (Mandatory Access Control) untuk semua subjects dan objects
- Implementation: SELinux, AppArmor

...dan seterusnya hingga AC-3(15)

---

## Control Baselines dan Tailoring

### Control Baselines (NIST SP 800-53B)

> [!CAUTION]
> Di Revision 5, **baselines dipindahkan** ke dokumen terpisah: **NIST SP 800-53B**.

**Tiga Level Baseline:**

| Impact Level | Deskripsi | Contoh Sistem |
|--------------|-----------|---------------|
| **Low** | Kehilangan kerahasiaan, integritas, atau ketersediaan memiliki dampak **terbatas** | Website informasi publik, sistem pelatihan internal |
| **Moderate** | Kehilangan memiliki dampak **serius** | Email kantor, sistem HR, intranet |
| **High** | Kehilangan memiliki dampak **parah atau catastrophic** | Sistem keuangan, infrastruktur kritis, PII sensitif |

**Cara Baseline Bekerja:**
1. **Kategorisasi sistem** berdasarkan FIPS 199
2. **Pilih baseline** (Low, Moderate, atau High)
3. **Terapkan kontrol** dari baseline tersebut
4. **Tailor** kontrol sesuai kebutuhan spesifik
5. **Implement dan assess** kontrol

### Tailoring Process (Penyesuaian Kontrol)

**Aktivitas Tailoring:**

1. **Identifying Unnecessary Controls**
   - Hilangkan kontrol yang tidak applicable
   - Contoh: Kontrol fisik untuk sistem cloud-only

2. **Specifying Compensating Controls**
   - Gunakan kontrol alternatif jika kontrol standar tidak bisa diimplementasi
   - Harus memberikan proteksi setara

3. **Assigning Specific Values to Parameters**
   - Contoh: "Review accounts [at least monthly]" → tentukan "every 2 weeks"

4. **Supplementing Baselines**
   - Tambahkan kontrol tambahan untuk risiko spesifik
   - Contoh: Tambah SR controls untuk supply chain risk yang tinggi

5. **Providing Additional Detail**
   - Elaborasi kontrol untuk konteks organisasi

### Overlays

**Apa itu Overlay?**
Overlay adalah **spesifikasi kontrol tambahan** atau **tailoring guidance** untuk use case atau teknologi tertentu.

**Contoh Overlay:**
- **Cloud Computing Overlay:** Kontrol khusus untuk cloud environments
- **Industrial Control Systems (ICS) Overlay:** Untuk SCADA dan operational technology
- **Privacy Overlay:** Penekanan pada kontrol privasi
- **Mobile Device Overlay:** Untuk mobile computing
- **Supply Chain Overlay:** Fokus pada SR family

---

## Integrasi dengan Risk Management Framework (RMF)

NIST SP 800-53 adalah bagian integral dari **Risk Management Framework (RMF)** yang didefinisikan dalam NIST SP 800-37.

### 7 Langkah RMF

```
┌──────────────────────────────────────────────────────┐
│  1. PREPARE                                          │
│  • Organization and system-level preparation         │
└──────────────────┬───────────────────────────────────┘
                   │
┌──────────────────▼───────────────────────────────────┐
│  2. CATEGORIZE                                       │
│  • Categorize system based on impact (FIPS 199)      │
└──────────────────┬───────────────────────────────────┘
                   │
┌──────────────────▼───────────────────────────────────┐
│  3. SELECT                                           │
│  • Select controls from SP 800-53 based on baseline  │
│  • Tailor controls                                   │
└──────────────────┬───────────────────────────────────┘
                   │
┌──────────────────▼───────────────────────────────────┐
│  4. IMPLEMENT                                        │
│  • Implement controls in the system                  │
│  • Document implementation                           │
└──────────────────┬───────────────────────────────────┘
                   │
┌──────────────────▼───────────────────────────────────┐
│  5. ASSESS                                           │
│  • Assess control effectiveness                      │
│  • Produce Security Assessment Report (SAR)          │
└──────────────────┬───────────────────────────────────┘
                   │
┌──────────────────▼───────────────────────────────────┐
│  6. AUTHORIZE                                        │
│  • Authorizing Official makes risk decision          │
│  • Issue Authorization to Operate (ATO)              │
└──────────────────┬───────────────────────────────────┘
                   │
┌──────────────────▼───────────────────────────────────┐
│  7. MONITOR                                          │
│  • Continuous monitoring of controls                 │
│  • Ongoing authorization                             │
└──────────────────────────────────────────────────────┘
```

---

## Integrasi Keamanan dan Privasi

> [!IMPORTANT]
> Salah satu perubahan terbesar di Revision 5 adalah **integrasi penuh** kontrol privasi ke dalam katalog utama.

### Mengapa Integrasi Penting?

**Sebelum Revision 5:**
- Kontrol privasi di Appendix J (terpisah)
- Security dan privacy dianggap domain berbeda
- Koordinasi sulit antara security dan privacy teams

**Revision 5:**
- Kontrol privasi terintegrasi penuh
- Security dan privacy saling melengkapi
- Unified approach untuk risk management

### Privacy Controls di Rev 5

**Keluarga Kontrol dengan Fokus Privacy:**
- **AC:** Access Control → privacy-relevant access restrictions
- **AU:** Audit and Accountability → logging PII access
- **IA:** Identification and Authentication → privacy-preserving authentication
- **PT:** PII Processing and Transparency → dedicated privacy family
- **SA:** System Acquisition → privacy requirements in procurement
- **SI:** System Integrity → PII quality and accuracy

### Privacy Principles

1. **Authority and Purpose**
   - Legal authority untuk collect PII
   - Purpose specification untuk penggunaan PII

2. **Data Minimization**
   - Hanya collect PII yang necessary
   - Retention limits

3. **Transparency**
   - Privacy notices
   - Disclosure tentang PII processing

4. **Individual Participation**
   - Access untuk melihat PII sendiri
   - Correction mechanisms

5. **Accountability and Auditing**
   - Documentation dan audit trails
   - Responsibility assignment

6. **Security**
   - Proteksi PII dari unauthorized access/disclosure
   - Encryption, access controls

7. **Data Quality and Integrity**
   - Accuracy dan completeness
   - Timeliness

---

## Assessment dan Monitoring

### Control Assessment

**Tujuan Assessment:**
- Menentukan apakah kontrol diimplementasi dengan benar
- Evaluasi efektivitas kontrol
- Identifikasi weaknesses dan deficiencies

**Assessment Methods (NIST SP 800-53A):**

1. **Examine (Periksa)**
   - Review dokumentasi, kebijakan, prosedur
   - Analisis spesifikasi, design, konfigurasi

2. **Interview (Wawancara)**
   - Tanya personel tentang proses dan procedures
   - Verifikasi understanding

3. **Test (Uji)**
   - Automated scanning
   - Penetration testing
   - Functional testing

**Depth of Assessment:**
- **Basic:** Minimal testing
- **Focused:** Targeted pada high-risk areas
- **Comprehensive:** In-depth evaluation semua kontrol

### Continuous Monitoring

**CA-7: Continuous Monitoring**

Organisasi harus mengembangkan strategi continuous monitoring yang mencakup:

**Komponen:**
1. **Configuration Management dan Control**
   - Baseline configurations
   - Change tracking

2. **Security Impact Analysis**
   - Evaluate changes untuk dampak keamanan

3. **Ongoing Control Assessment**
   - Regular testing dan evaluation

4. **Security Status Reporting**
   - Dashboard dan metrics
   - Executive reporting

5. **Active Involvement**
   - Incident response
   - Threat intelligence integration

**Metrics dan Measures:**
- Number of vulnerabilities (by severity)
- Patching compliance rate
- Account review compliance
- Incident response time
- Control effectiveness scores

---

## Implementasi Praktis

### Langkah-Langkah Implementasi

#### 1. Understand Your System

**Pertanyaan Kunci:**
- Apa fungsi sistem?
- Data apa yang diproses?
- Siapa users dan stakeholders?
- Di mana sistem di-host?
- Apa dependencies?

#### 2. Categorize (FIPS 199)

**Security Categorization:**
```
SC = {(confidentiality, impact), (integrity, impact), (availability, impact)}
```

**Impact Levels:**
- Low, Moderate, atau High untuk setiap security objective
- Overall impact = highest impact dari ketiga objectives

**Contoh:**
```
Email System:
- Confidentiality: Moderate (sensitive tapi bukan classified)
- Integrity: Moderate (important untuk business operations)
- Availability: Moderate (business disruption jika down)

Overall: MODERATE
```

#### 3. Select Baseline dan Tailor

**Pilih Baseline dari SP 800-53B:**
- Low impact → Low baseline
- Moderate impact → Moderate baseline
- High impact → High baseline

**Tailoring Steps:**
```
1. Review all controls in baseline
2. Identify tidak applicable → eliminate atau mark N/A
3. Specify parameter values
4. Add compensating controls jika needed
5. Add supplemental controls untuk specific risks
6. Document tailoring decisions
```

#### 4. Document dalam System Security Plan (SSP)

**SSP harus mencakup:**
- System description dan boundaries
- Security categorization
- Control selection dan tailoring rationale
- Implementation details untuk setiap kontrol
- Roles dan responsibilities
- Interconnections dengan sistem lain

#### 5. Implement Controls

**Implementation Tips:**
- ✅ Prioritize berdasarkan risk
- ✅ Leverage existing tools dan processes
- ✅ Document as you implement
- ✅ Train personel
- ✅ Test controls

#### 6. Assess Controls

**Assessment Planning:**
- Define scope dan objectives
- Select assessment methods
- Schedule assessments
- Assign assessor

**Deliverable:**
- **Security Assessment Report (SAR):** Findings, weaknesses, recommendations

#### 7. Remediate Weaknesses

**Plan of Action and Milestones (POA&M):**
```
For each weakness:
- Description
- Risk rating
- Remediation plan
- Responsible party
- Target completion date
- Resources required
```

#### 8. Continuous Monitoring

**Establish:**
- Monitoring strategy
- Automated tools (SIEM, vulnerability scanners)
- Review schedule
- Reporting mechanism

---

## Hubungan dengan Framework Lain

### NIST Cybersecurity Framework (CSF)

**Mapping SP 800-53 ke CSF:**

| CSF Function | SP 800-53 Families |
|--------------|-------------------|
| **Identify** | RA (Risk Assessment), PM (Program Management), PL (Planning) |
| **Protect** | AC, AT, CM, IA, MA, MP, PE, PS, SC, SI |
| **Detect** | AU (Audit), CA (Assessment), SI (Monitoring) |
| **Respond** | IR (Incident Response), CP (Contingency) |
| **Recover** | CP (Contingency Planning), IR |

### ISO/IEC 27001

**Kompatibilitas:**
- Banyak overlap antara SP 800-53 dan ISO 27001 Annex A
- SP 800-53 lebih detailed dan prescriptive
- ISO 27001 lebih framework-oriented

**Dual Implementation:**
- Organisasi bisa comply dengan keduanya
- SP 800-53 controls dapat map ke ISO controls

### GDPR dan Privacy Regulations

**PT Family untuk Privacy Compliance:**
- Supports GDPR requirements
- Data subject rights
- Privacy by design
- Data protection impact assessment (DPIA)

---

## Use Cases dan Contoh

### Use Case 1: Cloud-Based SaaS Application

**Sistem:** Customer Relationship Management (CRM) di AWS

**Kategorisasi:**
- Confidentiality: HIGH (customer PII)
- Integrity: MODERATE
- Availability: MODERATE
- **Overall: HIGH**

**Baseline:** High baseline dari SP 800-53B

**Tailoring Considerations:**
- Eliminate physical controls (PE) → infrastructure controlled oleh AWS
- Supplement dengan SC controls untuk encryption in transit/at rest
- Add PT controls untuk PII processing
- Implement AC-2(1) untuk MFA
- Use cloud-native monitoring untuk AU dan SI

**Key Controls:**
- AC-3: RBAC implementation
- IA-2(1): MFA for all users
- SC-28: Encryption at rest (AWS KMS)
- SC-13: FIPS 140-2 validated crypto
- AU-2: CloudWatch logging
- PT-5: Privacy notice untuk customers
- SR-2: Vendor assessment untuk AWS

### Use Case 2: On-Premise Industrial Control System (ICS)

**Sistem:** SCADA system untuk water treatment

**Kategorisasi:**
- Confidentiality: LOW
- Integrity: HIGH (safety-critical)
- Availability: HIGH (24/7 operations)
- **Overall: HIGH**

**Baseline:** High baseline + ICS Overlay

**Tailoring Considerations:**
- Emphasis pada SI (integrity) dan SC (boundary protection)
- Air-gap atau strict network segmentation
- Limited remote access
- Specialized training (AT) untuk operators
- Physical security (PE) critical

**Key Controls:**
- SC-7: Network segmentation, DMZ
- AC-17: Restricted remote access dengan strong auth
- SI-7: Software integrity verification
- CM-3: Strict change control
- CP: Redundancy dan failover
- PE-3: Physical access control ke control room

### Use Case 3: Mobile Application Processing Health Data

**Sistem:** Mobile health tracking app (iOS/Android)

**Kategorisasi:**
- Confidentiality: HIGH (HIPAA PHI)
- Integrity: MODERATE
- Availability: LOW
- **Overall: HIGH (due to HIPAA)**

**Baseline:** High baseline + Privacy Overlay

**Tailoring Considerations:**
- Mobile-specific controls
- App-level security (SA-11 developer testing)
- Device security (IA-3 device authentication)
- Encryption (SC-28 at rest, SC-8 in transit)
- Privacy (PT family extensively)

**Key Controls:**
- AC-20: Use of external systems (BYOD policy)
- IA-2: User authentication
- SC-28: Full disk encryption on device
- PT-2: Authority to process PHI
- PT-4: Consent mechanism
- PT-5: Privacy notice
- AU-2: Audit logging PII access
- MP-6: Media sanitization jika device lost

---

## Tips Implementasi dan Best Practices

### 🎯 Best Practice 1: Start Small

**Jangan:**
❌ Coba implement semua 1000+ controls sekaligus

**Lakukan:**
✅ Prioritize berdasarkan risk
✅ Implement baseline controls dulu
✅ Incremental improvements
✅ Focus pada high-impact, high-risk areas

### 🎯 Best Practice 2: Leverage Automation

**Tools yang Membantu:**
- **Configuration Management:** Ansible, Puppet, Chef
- **Vulnerability Scanning:** Nessus, Qualys, OpenVAS
- **SIEM:** Splunk, ELK, QRadar
- **Identity Management:** Okta, Azure AD, FreeIPA
- **Compliance:** OpenSCAP, InSpec, Chef Compliance

**Automate:**
- Control assessments (where possible)
- Continuous monitoring
- Reporting dan dashboards
- Remediation workflows

### 🎯 Best Practice 3: Documentation is Key

**Document Everything:**
- Tailoring decisions dan rationale
- Implementation details
- Assessment results
- Changes dan updates
- Exceptions dan risk acceptances

**Benefits:**
- Easier assessments dan audits
- Knowledge transfer
- Compliance evidence
- Continuous improvement

### 🎯 Best Practice 4: Integrate Security Early

**Security by Design:**
- SA-8: Apply security engineering principles
- Shift-left security
- Security requirements dalam procurement (SA-4)
- Developer security training

### 🎯 Best Practice 5: Don't Forget People

**Human Factor:**
- AT-2: Security awareness untuk ALL users
- AT-3: Role-based training
- PS-6: Access agreements
- Clear policies dan procedures (setiap family memiliki -1 control)

### 🎯 Best Practice 6: Continuous Improvement

**Mindset:**
- Security adalah journey, bukan destination
- Regular reviews dan updates
- Learn dari incidents
- Stay updated dengan threats dan patches

---

## Perubahan dari Revision 4 ke Revision 5

### Major Changes

| Aspek | Revision 4 | Revision 5 |
|-------|-----------|-----------|
| **Privacy** | Appendix terpisah (Appendix J) | Fully integrated dalam katalog |
| **Baselines** | Dalam SP 800-53 | Moved ke SP 800-53B |
| **Control Families** | 18 families | 20 families (tambah PT dan SR) |
| **Total Controls** | ~900 controls | ~1000+ controls |
| **Outcome Focus** | Lebih prescriptive | Lebih outcome-based |
| **Supply Chain** | Limited coverage | Dedicated SR family |

### New Controls dan Enhancements

**New Families:**
- **PT (PII Processing and Transparency):** 8 controls baru
- **SR (Supply Chain Risk Management):** 12 controls baru

**Enhanced Areas:**
- Supply chain security
- Privacy protections
- Insider threat mitigation
- Advanced persistent threats (APT)
- Cloud computing
- Mobile computing
- IoT dan operational technology

---

## Kesimpulan dan Rekomendasi

### Kesimpulan Utama

1. **Comprehensive Coverage**
   - SP 800-53r5 mencakup hampir semua aspek keamanan dan privasi
   - Applicable untuk berbagai jenis sistem dan organisasi

2. **Flexibility**
   - Tailoring memungkinkan customization
   - Overlays untuk use cases spesifik
   - Scalable dari small business hingga federal agencies

3. **Integration adalah Kunci**
   - Security DAN privacy harus dipertimbangkan together
   - Part of broader risk management strategy (RMF)
   - Alignment dengan framework lain (CSF, ISO, GDPR)

4. **Continuous Process**
   - Implementation bukan one-time project
   - Continuous monitoring dan improvement essential
   - Adapt to evolving threats

### Rekomendasi untuk Organisasi

#### Untuk Organisasi yang Baru Memulai

1. **Pahami Sistem Anda**
   - Inventory aset dan data
   - Understand business processes
   - Identify critical systems

2. **Mulai dengan Baseline**
   - Categorize systems
   - Apply appropriate baseline
   - Focus pada foundational controls dulu

3. **Build Gradually**
   - Implement high-priority controls
   - Document as you go
   - Learn dan iterate

#### Untuk Organisasi yang Sudah Mature

1. **Gap Analysis**
   - Compare current state vs Rev 5
   - Identify new controls (PT, SR)
   - Update documentation

2. **Enhance Automation**
   - Continuous monitoring
   - Automated assessment
   - Integration dengan DevSecOps

3. **Privacy Integration**
   - Assess PT controls
   - Collaborate security dan privacy teams
   - Update policies

### Next Steps

1. **Read Supporting Documents:**
   - NIST SP 800-53B (Baselines)
   - NIST SP 800-53A (Assessment Procedures)
   - NIST SP 800-37 (Risk Management Framework)

2. **Training dan Certification:**
   - Certified Information Systems Security Professional (CISSP)
   - Certified Information Security Manager (CISM)
   - NIST RMF training

3. **Community Engagement:**
   - NIST workshops dan conferences
   - Professional associations (ISSA, ISACA)
   - Industry-specific working groups

---

## Referensi dan Sumber Tambahan

### Dokumen NIST Terkait

- **NIST SP 800-53B:** Control Baselines for Information Systems and Organizations
- **NIST SP 800-53A:** Assessing Security and Privacy Controls
- **NIST SP 800-37:** Risk Management Framework (RMF)
- **NIST SP 800-207:** Zero Trust Architecture
- **NIST Cybersecurity Framework (CSF)**
- **FIPS 199:** Standards for Security Categorization
- **FIPS 200:** Minimum Security Requirements

### Tools dan Resources

- **OpenSCAP:** Open-source compliance scanning
- **NIST National Vulnerability Database (NVD)**
- **NIST Computer Security Resource Center (CSRC):** https://csrc.nist.gov

---

## Glosarium Singkat

| Istilah | Penjelasan |
|---------|-----------|
| **ATO** | Authorization to Operate - izin operasional untuk sistem |
| **Baseline** | Set minimum kontrol untuk impact level tertentu |
| **Control** | Safeguard atau countermeasure untuk melindungi sistem |
| **Control Enhancement** | Augmentasi untuk memperkuat control dasar |
| **FIPS** | Federal Information Processing Standards |
| **Impact Level** | Low, Moderate, atau High berdasarkan dampak |
| **Overlay** | Tailoring guidance untuk teknologi atau use case spesifik |
| **PII** | Personally Identifiable Information |
| **POA&M** | Plan of Action and Milestones |
| **RMF** | Risk Management Framework |
| **SAR** | Security Assessment Report |
| **SSP** | System Security Plan |
| **Tailoring** | Penyesuaian kontrol untuk konteks spesifik |

---

**Catatan Penting:**

> [!WARNING]
> Implementasi NIST SP 800-53 memerlukan komitmen organisation-wide. Ini bukan tanggung jawab security team saja, tetapi melibatkan semua stakeholder dari executive hingga end users.

**Dokumen ini berdasarkan:** NIST Special Publication 800-53 Revision 5 (September 2020, updated December 2020)

**Untuk informasi terbaru, selalu rujuk ke:** https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final
