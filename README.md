# Learning Zero Trust Architecture (ZTA)

Repositori pembelajaran komprehensif tentang **Zero Trust Architecture** dan **Digital Identity Guidelines** berdasarkan publikasi NIST (National Institute of Standards and Technology).

## 🎮 Interactive Quiz - Test Your Knowledge!

**NEW!** Uji pemahaman Anda dengan quiz interactive yang fun dan educational:

👉 **[PLAY QUIZ NOW!](https://urobin84.github.io/learning-zta/quiz.html)** 👈

- 🌱 **Pemula:** 10 pertanyaan dasar
- ⚡ **Menengah:** 15 pertanyaan untuk yang sudah paham konsep
- 🔥 **Expert:** 20 pertanyaan hardcore challenge!

✨ Features:
- Real-time scoring dengan visual feedback
- Penjelasan detail untuk setiap jawaban
- Mobile-friendly & zero installation needed
- Perfect untuk self-assessment!

**Challenge:** Bisa score 90%+ di Expert mode? 🏆

---

## 📚 Daftar Isi

- [🎮 Interactive Quiz](#-interactive-quiz---test-your-knowledge)
- [Tentang Repositori Ini](#-tentang-repositori-ini)
- [Struktur Folder](#-struktur-folder)
- [Dokumen Sumber (PDF)](#-dokumen-sumber-pdf)
- [Penjelasan dalam Bahasa Indonesia](#-penjelasan-dalam-bahasa-indonesia)
- [Cara Menggunakan](#-cara-menggunakan)
- [Roadmap Pembelajaran](#-roadmap-pembelajaran)
- [Referensi dan Sumber](#-referensi-dan-sumber)
- [Mapping Dokumen ke Use Cases](#-mapping-dokumen-ke-use-cases)
- [Lisensi dan Disclaimer](#-lisensi-dan-disclaimer)
- [Feedback dan Kontribusi](#-feedback-dan-kontribusi)

---

## 🎯 Tentang Repositori Ini

Repositori ini berisi:
- **Dokumen PDF asli** dari NIST tentang Zero Trust Architecture dan Digital Identity
- **Penjelasan lengkap dalam bahasa Indonesia** untuk setiap dokumen
- **Panduan implementasi** dan testing criteria
- **Best practices** untuk compliance dan security

### Mengapa Zero Trust?

Zero Trust Architecture adalah paradigma keamanan modern yang berprinsip:
- ❌ **Never trust, always verify** - Tidak ada kepercayaan implisit
- 🔒 **Least privilege access** - Akses minimum yang diperlukan
- 🚨 **Assume breach** - Selalu bersiap untuk insiden

---

## 📁 Struktur Folder

```
learning-zta/
├── README.md                          # File ini
├── pdfs/                             # Dokumen PDF asli dari NIST
│   ├── 800-63A Conformance Criteria_0620.pdf
│   ├── 800-63B Conformance Criteria_0620.pdf
│   ├── 800-63C Conformance Criteria_042621.pdf
│   ├── NIST.CSWP.29.pdf
│   ├── NIST.SP.800-53r5.pdf
│   ├── SP-800-63-3-Implementation-Resources_07012020.pdf
│   ├── nist.sp.800-207.pdf
│   └── zta-nist-sp-1800-35e-preliminary-draft.pdf
│
└── penjelasan/                       # Penjelasan dalam Bahasa Indonesia
    ├── penjelasan-nist-800-63-conformance-criteria.md
    ├── penjelasan-nist-csf-2.0.md
    ├── penjelasan-nist-sp-800-207.md
    ├── penjelasan-nist-sp-800-53r5.md
    ├── penjelasan-nist-sp-800-63-3.md
    └── penjelasan-nist-zta.md
```

---

## 📄 Dokumen Sumber (PDF)

### Zero Trust Architecture

| Dokumen | Halaman | Tanggal | Deskripsi |
|---------|---------|---------|-----------|
| **nist.sp.800-207.pdf** | 59 | Aug 2020 | Dokumen fundamental tentang Zero Trust Architecture - definisi, prinsip, komponen, dan deployment models |
| **zta-nist-sp-1800-35e-preliminary-draft.pdf** | 65 | Dec 2022 | Volume E: Risk and Compliance Management untuk implementasi ZTA |

### Digital Identity Guidelines

| Dokumen | Halaman | Tanggal | Deskripsi |
|---------|---------|---------|-----------|
| **SP-800-63-3-Implementation-Resources_07012020.pdf** | 82 | Jul 2020 | Panduan implementasi praktis untuk Digital Identity (IAL, AAL, FAL) |
| **800-63A Conformance Criteria_0620.pdf** | ~47 | Jun 2020 | Testing criteria untuk Identity Proofing dan Enrollment |
| **800-63B Conformance Criteria_0620.pdf** | 106 | Jun 2020 | Testing criteria untuk Authentication dan Lifecycle Management |
| **800-63C Conformance Criteria_042621.pdf** | 68 | Apr 2021 | Testing criteria untuk Federation dan Assertions |

### Security Controls & Frameworks

| Dokumen | Halaman | Tanggal | Deskripsi |
|---------|---------|---------|-----------|
| **NIST.SP.800-53r5.pdf** | 492 | Sep 2020 | Katalog komprehensif Security and Privacy Controls (20 control families) |
| **NIST.CSWP.29.pdf** | 32 | Feb 2024 | NIST Cybersecurity Framework (CSF) 2.0 - framework risk management terbaru |

---

## 📖 Penjelasan dalam Bahasa Indonesia

### 1. Zero Trust Architecture

#### [penjelasan-nist-sp-800-207.md](penjelasan/penjelasan-nist-sp-800-207.md)
**Topik:**
- ✅ 7 Prinsip Dasar Zero Trust
- ✅ Komponen Logis: Policy Engine, Policy Administrator, Policy Enforcement Point
- ✅ 4 Model Deployment (Device Agent, Enclave-Based, Resource Portal, Sandboxing)
- ✅ Threat Models dan Mitigasi
- ✅ Panduan Migrasi 7 Langkah

#### [penjelasan-nist-zta.md](penjelasan/penjelasan-nist-zta.md)
**Topik:**
- ✅ Risk and Compliance Management untuk ZTA
- ✅ Pemetaan ke NIST CSF, SP 800-53, Executive Order 14028
- ✅ Manajemen Risiko: Threats, Vulnerabilities, Solutions

### 2. Digital Identity

#### [penjelasan-nist-sp-800-63-3.md](penjelasan/penjelasan-nist-sp-800-63-3.md)
**Topik:**
- ✅ **IAL (Identity Assurance Levels):** IAL1, IAL2, IAL3
  - Resolution, Validation, Verification phases
- ✅ **AAL (Authenticator Assurance Levels):** AAL1, AAL2, AAL3
  - 9 tipe authenticator (Password, OTP, Cryptographic, Biometric)
  - MFA requirements
- ✅ **FAL (Federation Assurance Levels):** FAL1, FAL2, FAL3
  - SAML dan OpenID Connect
  - Privacy-preserving federation
- ✅ Use Cases: E-commerce, Banking, Healthcare, Government

#### [penjelasan-nist-800-63-conformance-criteria.md](penjelasan/penjelasan-nist-800-63-conformance-criteria.md)
**Topik:**
- ✅ **Testing Methodology:** EXAMINE, INTERVIEW, TEST
- ✅ **Part A:** Identity Proofing Testing
  - Evidence validation
  - Biometric matching
  - KBV testing
- ✅ **Part B:** Authentication Testing (106 halaman)
  - Password policy validation
  - OOB/OTP testing
  - FIPS 140 compliance
  - Session management
- ✅ **Part C:** Federation Testing (68 halaman)
  - Assertion validation
  - Replay protection
  - Privacy testing
- ✅ Practical test cases, common pitfalls, audit execution
- ✅ Tools dan resources

### 3. Security Controls & Frameworks

#### [penjelasan-nist-sp-800-53r5.md](penjelasan/penjelasan-nist-sp-800-53r5.md)
**Topik:**
- ✅ **20 Keluarga Kontrol:** AC, AU, IA, SC, SI, SR (Supply Chain), PT (Privacy), dll.
- ✅ Control Structure: Statement, Discussion, Enhancements
- ✅ **Baselines:** Low, Moderate, High impact levels
- ✅ Tailoring process
- ✅ Integrasi dengan Risk Management Framework (RMF)
- ✅ Privacy integration (baru di Rev 5)
- ✅ Use cases praktis

#### [penjelasan-nist-csf-2.0.md](penjelasan/penjelasan-nist-csf-2.0.md)
**Topik:**
- ✅ **6 Fungsi Utama:** GOVERN (baru!), IDENTIFY, PROTECT, DETECT, RESPOND, RECOVER
- ✅ **CSF Core:** Functions → Categories → Subcategories
- ✅ **CSF Profiles:** Current vs Target state, gap analysis
- ✅ **CSF Tiers:** 1-4 (Partial → Adaptive)
- ✅ Risk communication dengan executives
- ✅ Integrasi dengan Enterprise Risk Management
- ✅ Implementation roadmap

---

## 🚀 Cara Menggunakan

### Untuk Pemula

1. **Mulai dengan CSF 2.0** untuk memahami framework overview
   - Baca: [penjelasan-nist-csf-2.0.md](penjelasan/penjelasan-nist-csf-2.0.md)
   - Fokus pada 6 fungsi utama

2. **Pelajari Zero Trust Fundamentals**
   - Baca: [penjelasan-nist-sp-800-207.md](penjelasan/penjelasan-nist-sp-800-207.md)
   - Pahami 7 prinsip ZT dan komponen logis

3. **Eksplorasi Digital Identity**
   - Baca: [penjelasan-nist-sp-800-63-3.md](penjelasan/penjelasan-nist-sp-800-63-3.md)
   - Pahami IAL, AAL, FAL

### Untuk Implementers

1. **Assess Current State**
   - Gunakan CSF Profiles untuk gap analysis
   - Review SP 800-53r5 untuk kontrol yang diperlukan

2. **Plan Implementation**
   - Ikuti roadmap di SP 800-207 untuk ZTA
   - Pilih IAL/AAL/FAL yang sesuai dengan risk appetite

3. **Implement dan Test**
   - Gunakan Implementation Resources sebagai panduan
   - Validasi dengan Conformance Criteria

### Untuk Auditors

1. **Review Conformance Criteria**
   - Baca: [penjelasan-nist-800-63-conformance-criteria.md](penjelasan/penjelasan-nist-800-63-conformance-criteria.md)
   - Siapkan testing methodology

2. **Prepare Audit Checklist**
   - Gunakan criteria dari SP 800-63A/B/C
   - Map ke SP 800-53r5 controls

3. **Conduct Assessment**
   - EXAMINE documents
   - INTERVIEW personnel
   - TEST implementations

---

## 📚 Roadmap Pembelajaran

### Level 1: Foundation (1-2 minggu)

**Tujuan:** Memahami konsep dasar

```
Week 1:
  □ Baca penjelasan-nist-csf-2.0.md (6 fungsi)
  □ Baca penjelasan-nist-sp-800-207.md (7 prinsip ZT)
  
Week 2:
  □ Baca penjelasan-nist-sp-800-63-3.md (IAL/AAL/FAL overview)
  □ Review use cases praktis
```

### Level 2: Implementation (2-4 minggu)

**Tujuan:** Memahami cara implementasi

```
Week 3-4:
  □ Deep dive ke SP 800-207 deployment models
  □ Pilih authenticator types untuk AAL requirements
  □ Study federation protocols (SAML/OIDC)
  
Week 5-6:
  □ Review SP 800-53r5 control families
  □ Map requirements ke controls
  □ Create implementation plan
```

### Level 3: Advanced (4-8 minggu)

**Tujuan:** Mastery dan compliance

```
Week 7-10:
  □ Study conformance criteria untuk testing
  □ Develop testing methodology
  □ Create audit checklists
  
Week 11-14:
  □ Implement pilot ZTA
  □ Self-assessment dengan conformance criteria
  □ Iterate dan improve
```

---

## 🔗 Referensi dan Sumber

### Official NIST Resources

- **NIST Computer Security Resource Center (CSRC):** https://csrc.nist.gov/
- **NIST Cybersecurity Framework:** https://www.nist.gov/cyberframework
- **NIST Digital Identity Guidelines:** https://pages.nist.gov/800-63-3/
- **NIST Implementation Resources:** https://pages.nist.gov/800-63-3-Implementation-Resources/

### Related Standards

- **FIDO Alliance:** https://fidoalliance.org/ (phishing-resistant authentication)
- **ISO/IEC 27001:** Information Security Management
- **GDPR:** EU General Data Protection Regulation
- **HIPAA:** Health Insurance Portability and Accountability Act

### Tools & Communities

- **OpenSCAP:** Open-source compliance scanning
- **NIST National Vulnerability Database (NVD):** https://nvd.nist.gov/
- **NIST Cybersecurity Community:** Workshops dan conferences

---

## 📊 Mapping Dokumen ke Use Cases

### Use Case 1: Implementasi Zero Trust untuk Enterprise

**Dokumen yang Relevan:**
1. ✅ SP 800-207 (Architecture fundamentals)
2. ✅ CSF 2.0 (Risk management framework)
3. ✅ SP 800-53r5 (Security controls untuk implement)
4. ✅ SP 1800-35E (Compliance mapping)

### Use Case 2: Digital Identity untuk Banking App

**Dokumen yang Relevan:**
1. ✅ SP 800-63-3 Implementation Resources (IAL2/AAL2 guidance)
2. ✅ 800-63A/B Conformance Criteria (Testing)
3. ✅ SP 800-53r5 (IA, AC, AU controls)

### Use Case 3: Federation SSO untuk Cloud Apps

**Dokumen yang Relevan:**
1. ✅ SP 800-63-3 Implementation Resources (FAL guidance)
2. ✅ 800-63C Conformance Criteria (Federation testing)
3. ✅ SP 800-207 (ZTA for cloud)

### Use Case 4: Compliance Audit Preparation

**Dokumen yang Relevan:**
1. ✅ Semua Conformance Criteria (Testing checklists)
2. ✅ SP 800-53r5 (Control catalog)
3. ✅ CSF 2.0 (Framework mapping)

---

## 🎓 Kontributor

Dokumentasi penjelasan dalam bahasa Indonesia dibuat untuk mempermudah pemahaman konsep-konsep NIST bagi praktisi, auditor, dan pengembang di Indonesia.

---

## 📝 Lisensi dan Disclaimer

### Status Copyright NIST Publications

Semua publikasi NIST adalah **karya pemerintah US Federal** dan masuk **Public Domain** sesuai dengan 17 U.S.C. §105:

> *"NIST publications are available in the public domain and are not subject to copyright in the United States."*

**Ini berarti:**
- ✅ Bebas digunakan tanpa izin
- ✅ Dapat dimodifikasi dan didistribusikan
- ✅ Tidak ada biaya lisensi
- ✅ Legal untuk tujuan komersial atau non-komersial

### Disclaimer Repository Ini

**⚠️ PENTING:** Repository ini adalah **sumber edukasi independen** dan **BUKAN official NIST resource**.

- 📚 **Dokumen PDF:** Publikasi original NIST (public domain)
- 📝 **Penjelasan & Quiz:** Dibuat untuk tujuan pembelajaran
- 🎯 **Tujuan:** Memudahkan pemahaman konsep NIST dalam Bahasa Indonesia
- ⚖️ **Compliance:** Selalu rujuk ke dokumen NIST asli untuk official compliance purposes
- 🚫 **Tidak ada afiliasi:** Tidak terafiliasi, disponsori, atau diendorse oleh NIST

### Referensi Legal

- **17 U.S.C. §105** - US Copyright Law (Government Works)
- **NIST Copyright Policy:** https://www.nist.gov/oism/copyrights
- **NIST Publications Portal:** https://csrc.nist.gov/publications

---

## 📮 Feedback dan Kontribusi

Jika menemukan kesalahan atau ingin berkontribusi:
- Buat issue untuk diskusi
- Pull request untuk perbaikan
- Sharing knowledge untuk komunitas

---

**Terakhir diupdate:** 14 Januari 2026

**Versi dokumen:**
- NIST SP 800-207: August 2020
- NIST SP 800-53r5: September 2020 (updated December 2020)
- NIST SP 800-63-3: June 2017 (Implementation Resources: July 2020)
- NIST CSF 2.0: February 2024

---

> **"Security is not a product, but a process. Zero Trust is not a destination, but a journey."**

Happy Learning! 🚀🔒
