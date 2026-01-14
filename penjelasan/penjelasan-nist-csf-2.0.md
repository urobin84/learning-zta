# Penjelasan NIST Cybersecurity Framework (CSF) 2.0

## Informasi Dokumen

**Judul Lengkap:** The NIST Cybersecurity Framework (CSF) 2.0

**Nomor Seri:** NIST Cybersecurity White Paper (CSWP) 29

**Status:** Final (Publikasi Resmi)

**Tanggal Publikasi:** 26 Februari 2024

**Jumlah Halaman:** 32 halaman

**DOI:** https://doi.org/10.6028/NIST.CSWP.29

**Kata Kunci:** Cybersecurity Framework, Risk Management, Cybersecurity Governance, GOVERN Function, Risk Communication

---

## Ringkasan Eksekutif

> [!IMPORTANT]
> NIST Cybersecurity Framework (CSF) 2.0 adalah **pembaruan major** dari framework yang pertama kali diluncurkan tahun 2014. Ini adalah panduan risk-based, voluntary untuk membantu organisasi dari semua ukuran dan sektor mengelola dan mengurangi risiko keamanan siber.

**Perubahan Signifikan di Versi 2.0:**
- ✨ **Fungsi Baru: GOVERN** - Menjadi pusat yang menginformasikan lima fungsi lainnya
- 🌍 **Perluasan Audiens** - Tidak lagi terbatas pada infrastruktur kritis, tetapi untuk **semua organisasi**
- 🔗 **Integrasi Risiko** - Menekankan bahwa cybersecurity risk harus dikelola bersama risiko enterprise lainnya
- 💬 **Komunikasi Lebih Baik** - Menjembatani gap antara eksekutif dan technical teams

---

## Apa itu NIST Cybersecurity Framework?

### Definisi

**NIST Cybersecurity Framework** adalah kerangka kerja sukarela yang menyediakan:
- **Bahasa umum** untuk memahami, mengelola, dan mengekspresikan risiko keamanan siber
- **Taksonomi hasil (outcomes)** keamanan siber yang tingkat tinggi
- **Metodologi** untuk mengimprovement program keamanan siber

### Tujuan Utama

1. **Describe (Mendeskripsikan)**
   - Current cybersecurity posture organisasi
   - Target state yang diinginkan

2. **Communicate (Mengkomunikasikan)**
   - Kebutuhan dan prioritas cybersecurity
   - Di antara stakeholders internal dan eksternal

3. **Prioritize (Memprioritaskan)**
   - Tindakan improvement
   - Berdasarkan business drivers dan risk tolerance

4. **Assess (Menilai)**
   - Progress terhadap target state
   - Identifikasi gaps

### Siapa yang Menggunakan CSF?

**Target Audiens (Diperluas di 2.0):**
- ✅ Semua ukuran organisasi (dari startup hingga enterprise)
- ✅ Semua sektor (private, public, nonprofit, academic)
- ✅ Infrastruktur kritis (traditional focus)
- ✅ SMEs (Small and Medium Enterprises)
- ✅ Organisasi global (bukan hanya US)

**Stakeholders:**
- **C-Suite Executives** (CEO, CISO, CIO, CFO)
- **Board of Directors**
- **Risk Managers**
- **Security Practitioners**
- **IT Professionals**
- **Procurement Officers**
- **Auditors dan Assessors**

---

## Komponen Utama CSF 2.0

CSF terdiri dari tiga komponen utama:

### 1. CSF Core (Inti Framework)

**Apa itu Core?**
- Set hasil (outcomes) keamanan siber yang diinginkan
- Terorganisir dalam hierarki: Functions → Categories → Subcategories

**Struktur:**
```
Functions (6)
    ↓
Categories (23)
    ↓
Subcategories (100+)
```

### 2. CSF Profiles (Profil)

**Apa itu Profile?**
- Penyesuaian CSF Core untuk kebutuhan spesifik organisasi
- Alignment antara requirements, risk tolerance, dan resources

**Jenis:**
- **Current Profile:** Di mana organisasi saat ini
- **Target Profile:** Di mana organisasi ingin berada

### 3. CSF Tiers (Tingkatan)

**Apa itu Tiers?**
- Karakterisasi tingkat keketatan (rigor) dalam praktik manajemen risiko cybersecurity
- Membantu organisasi memahami maturity posture-nya

**Empat Tingkatan:**
1. **Tier 1: Partial**
2. **Tier 2: Risk Informed**
3. **Tier 3: Repeatable**
4. **Tier 4: Adaptive**

---

## CSF Core: Enam Fungsi Utama

> [!NOTE]
> Fungsi **GOVERN** adalah penambahan BARU di CSF 2.0 dan menjadi fondasi dari lima fungsi lainnya.

### Hierarki Fungsi dalam CSF 2.0

```
┌─────────────────────────────────────────────────┐
│           GOVERN (GV) - BARU!                   │
│  Establishes and Monitors the Organization's    │
│  Cybersecurity Risk Management Strategy         │
└───────────┬─────────────────────────────────────┘
            │
            ├─────── Informs all functions below ──────┐
            │                                           │
    ┌───────▼───────┐  ┌──────────┐  ┌─────────┐     │
    │   IDENTIFY    │  │ PROTECT  │  │ DETECT  │     │
    └───────────────┘  └──────────┘  └─────────┘     │
                                                       │
            ┌──────────────────────────────────────────┘
            │
    ┌───────▼───────┐  ┌──────────┐
    │    RESPOND    │  │ RECOVER  │
    └───────────────┘  └──────────┘
```

---

### 1. GOVERN (GV) - ⭐ BARU DI 2.0 ⭐

**Deskripsi:**
Menetapkan dan memonitor strategi, ekspektasi, dan kebijakan manajemen risiko keamanan siber organisasi.

**Mengapa Penting:**
- GOVERN adalah **fondasi** - memberi konteks untuk semua fungsi lainnya
- Menegaskan bahwa cybersecurity adalah **business concern**, bukan hanya IT concern
- Memastikan accountability di tingkat leadership

**Categories dalam GOVERN:**

#### GV.OC - Organizational Context
- Memahami misi, stakeholders, dan tempat organisasi dalam ekosistem yang lebih luas
- Cybersecurity risk dipahami dalam konteks business objectives

#### GV.RM - Risk Management Strategy
- Menetapkan priorities, constraints, risk tolerance, dan assumptions
- Mendukung keputusan risk decisions

#### GV.OV - Roles, Responsibilities, and Authorities
- Clear accountability untuk cybersecurity
- Roles dan responsibilities didefinisikan dan dikomunikasikan

#### GV.PO - Policy
- Kebijakan organisasi untuk cybersecurity
- Translasi strategy menjadi actionable direction

#### GV.SC - Cybersecurity Supply Chain Risk Management
- Mengidentifikasi, assess, dan manage risiko supply chain
- Vendor dan third-party risk management

#### GV.RR - Cybersecurity Risk Management is Integrated
- Cybersecurity terintegrasi dengan enterprise risk management
- Sinergi dengan finance, privacy, physical security

**Contoh Subcategories:**
```
GV.OC-01: Organizational context dipahami
GV.RM-01: Risk management strategy established
GV.OV-01: Cybersecurity roles dan responsibilities assigned
GV.PO-01: Policy untuk cybersecurity established
GV.SC-01: Supply chain risk management process identified
GV.RR-01: Cybersecurity risks integrated dalam ERM
```

---

### 2. IDENTIFY (ID)

**Deskripsi:**
Mengembangkan pemahaman organisasi untuk mengelola risiko keamanan siber terhadap sistem, people, aset, data, dan capabilities.

**Tujuan:**
- Tahu apa yang perlu dilindungi
- Memahami business context
- Identifikasi risiko

**Key Categories:**

#### ID.AM - Asset Management
- Inventory physical devices dan systems
- Inventory software platforms dan applications
- External information systems identification

#### ID.RA - Risk Assessment
- Identifikasi vulnerabilities
- Threat intelligence
- Dikategorisasi dan prioritaskan risiko

#### ID.IM - Improvement
- Improvement opportunities diidentifikasi dari lessons learned
- Continuous improvement process

**Contoh Outcomes:**
- Semua hardware assets ter-inventarisasi
- Semua software dan applications ter-katalog
- Data flows dipetakan
- Threat intelligence dikonsumsi
- Vulnerabilities diidentifikasi dan diprioritaskan

---

### 3. PROTECT (PR)

**Deskripsi:**
Menggunakan safeguards untuk memastikan delivery layanan infrastruktur kritis.

**Tujuan:**
- Limitasi atau contain dampak potential cybersecurity event
- Implementasi kontrol keamanan

**Key Categories:**

#### PR.AA - Identity Management, Authentication and Access Control
- Identitas dan credentials dikelola
- Access control (physical dan logical)
- Remote access dikelola

#### PR.AT - Awareness and Training
- Personel terlatih dan aware tentang cybersecurity
- Privileged users memahami roles dan responsibilities

#### PR.DS - Data Security
- Data-at-rest dilindungi
- Data-in-transit dilindungi
- Manajemen aset (assets) data

#### PR.PS - Platform Security
- Configuration management
- Baseline configurations
- Patch management
- Removable media protections

#### PR.IR - Technology Infrastructure Resilience
- Backup dan redundansi
- Disaster recovery capabilities

**Contoh Outcomes:**
- MFA diimplementasikan untuk semua users
- Security awareness training untuk semua employees
- Data dienkripsi at rest dan in transit
- System configurations managed dan monitored
- Backups dilakukan secara teratur

---

### 4. DETECT (DE)

**Deskripsi:**
Temukan dan analyze possible cybersecurity attacks dan compromises.

**Tujuan:**
- Timely discovery of cybersecurity events
- Deteksi anomalies dan events

**Key Categories:**

#### DE.CM - Continuous Monitoring
- Networks dan physical environment dimonitor
- Personnel activity dimonitor
- Malicious code dideteksi

#### DE.AE - Adverse Event Analysis
- Event data dianalisis untuk mendeteksi cybersecurity incidents
- Impact dari events dipahami
- Incident alert thresholds established

**Contoh Outcomes:**
- SIEM deployed dan actively monitoring
- IDS/IPS di tempatnya
- Anomaly detection untuk user behavior
- Log aggregation dan correlation
- Security events ter-prioritas untuk response

---

### 5. RESPOND (RS)

**Deskripsi:**
Mengambil action terhadap detected cybersecurity incident.

**Tujuan:**
- Contain impact dari incidents
- Eradicate threats
- Response yang terkoordinasi

**Key Categories:**

#### RS.MA - Incident Management
- Incidents dikelola
- Incident response plans diexecute
- Incidents direport sesuai requirements

#### RS.AN - Incident Analysis
- Investigasi incidents
- Understand impact dan scope
- Forensic analysis

#### RS.RP - Incident Response Reporting and Communication
- Response activities dicoordinate dengan stakeholders
- Internal dan external communications
- Public disclosure (jika diperlukan)

#### RS.MI - Incident Mitigation
- Incidents contained
- Dimitigasi
- Newly identified vulnerabilities mitigated atau documented

**Contoh Outcomes:**
- Incident response plan ada dan tested
- Incident response team established
- Containment, eradication, dan recovery procedures defined
- Communication plan untuk stakeholders
- Lessons learned dari incidents

---

### 6. RECOVER (RC)

**Deskripsi:**
Restore capabilities atau services yang ter-impair karena cybersecurity incident.

**Tujuan:**
- Timely recovery ke normal operations
- Restore reputation
- Learn dari incident

**Key Categories:**

#### RC.RP - Incident Recovery Plan Execution
- Recovery plans executed selama atau setelah incident
- Restorasi dari backups

#### RC.CO - Incident Recovery Communication
- Public relations managed
- Reputation restored
- Recovery activities dikomunikasikan ke stakeholders

#### RC.HL - Incident Recovery Improvement
- Lessons learned incorporated ke future operations
- Recovery processes updated

**Contoh Outcomes:**
- Recovery priorities established berdasarkan business criticality
- Restoration verified sebelum return to production
- Recovery time objectives (RTOs) defined dan met
- Post-incident reviews conducted
- Improvements implemented

---

## CSF Profiles

### Apa itu Profile?

**Definisi:**
Profile adalah mekanisme untuk mendeskripsikan **current state** atau **desired target state** dari cybersecurity activities organisasi.

### Jenis Profiles

#### 1. Current Profile
- **"Where we are now"**
- Status cybersecurity outcomes saat ini
- Based on assessment atau audit

#### 2. Target Profile
- **"Where we want to be"**
- Desired cybersecurity outcomes
- Aligned dengan business goals, threat landscape, dan regulations

### Membuat Profile

**Langkah-Langkah:**

1. **Establish Scope**
   - Tentukan bagian organisasi atau system untuk di-profile
   - Full organization vs specific business units

2. **Identify Relevant Subcategories**
   - Pilih dari CSF Core semua subcategories yang applicable
   - Dapat menambahkan subcategories custom

3. **Prioritize**
   - Rank subcategories based on business importance
   - Risk-based prioritization

4. **Document Current State**
   - Assess implementation level untuk setiap subcategory
   - Current Profile created

5. **Define Target State**
   - Determine desired outcomes
   - Target Profile created

6. **Gap Analysis**
   - Compare Current vs Target
   - Identifikasi gaps

7. **Action Plan**
   - Prioritize gaps untuk remediation
   - Develop roadmap

### Contoh Profile Use Case

**Scenario:** Financial Services Company

**Scope:** Online Banking Platform

**High Priority Subcategories:**
- ID.AM-1: Physical devices dan systems diinventarisasi
- PR.AA-1: Identities dan credentials dikelola
- PR.DS-1: Data-at-rest dilindungi
- DE.CM-1: Network dimonitor untuk mendeteksi events
- RS.MA-1: Incident response plan diexecute

**Gap Analysis:**
```
Subcategory    Current  Target  Gap
PR.AA-1 (MFA)    60%     100%   40% → Priority 1
PR.DS-1 (Encryption) 80% 100%  20% → Priority 2
DE.CM-1 (SIEM)   40%     90%    50% → Priority 1
```

**Action Plan:**
1. Q1: Implement MFA untuk all users
2. Q2: Deploy SIEM solution
3. Q3: Full encryption untuk databases

---

## CSF Tiers (Tingkatan)

### Apa itu Tiers?

Tiers mendeskripsikan **tingkat keketatan** (degree of rigor) dalam praktik cybersecurity risk management organisasi.

> [!NOTE]
> Tiers BUKAN maturity model. Higher tier tidak selalu lebih baik - organisasi harus pilih tier yang sesuai dengan risk tolerance, threat environment, dan resources.

### Empat Tier

#### Tier 1: Partial

**Karakteristik:**
- **Risk Management Process:** Ad hoc, reaktif
- **Integrated Risk Management:** Limited awareness tentang cybersecurity risk di organizational level
- **External Participation:** Tidak memahami role dalam larger ecosystem

**Indikator:**
- ❌ Tidak ada formalized cybersecurity program
- ❌ Awareness terbatas pada individu dan teams tertentu
- ❌ Priority ditentukan setelah incident terjadi

**Cocok untuk:**
- Very small organizations dengan limited resources
- Low-risk environments
- Organizations di awal cybersecurity journey

#### Tier 2: Risk Informed

**Karakteristik:**
- **Risk Management Process:** Risk management practices approved tetapi mungkin belum organization-wide
- **Integrated Risk Management:** Awareness tentang cybersecurity risk but not enterprise-wide
- **External Participation:** Tahu role dalam ecosystem tetapi belum collaborate

**Indikator:**
- ✅ Cybersecurity policies ada
- ⚠️ Implementation tidak konsisten
- ⚠️ Risk informed tapi tidak fully integrated

**Cocok untuk:**
- Organizations dengan emerging cybersecurity programs
- Moderate risk environments
- Resource constraints

#### Tier 3: Repeatable

**Karakteristik:**
- **Risk Management Process:** Formalized policies, regularly updated
- **Integrated Risk Management:** Cybersecurity risk integrated dengan enterprise risk
- **External Participation:** Understands dependencies dan partners

**Indikator:**
- ✅ Consistent cybersecurity practices across organization
- ✅ Regular updates berdasarkan risk changes
- ✅ Personnel trained dan aware
- ✅ Collaborate dengan partners

**Cocok untuk:**
- Most mid to large organizations
- Regulated industries
- Organizations dengan mature security programs

#### Tier 4: Adaptive

**Karakteristik:**
- **Risk Management Process:** Adaptive, berdasarkan lessons learned dan predictive indicators
- **Integrated Risk Management:** Fully integrated, real-time risk awareness
- **External Participation:** Actively shares information, contributes to wider ecosystem

**Indikator:**
- ✅ Continuous improvement culture
- ✅ Advanced threat intelligence
- ✅ Proactive risk management
- ✅ Industry leadership

**Cocok untuk:**
- Critical infrastructure
- High-value targets
- Organizations dengan advanced security maturity

### Tiers Comparison Table

| Aspek | Tier 1 | Tier 2 | Tier 3 | Tier 4 |
|-------|--------|--------|--------|--------|
| **Risk Process** | Ad hoc | Approved by management | Formally approved | Adaptive |
| **Integration** | Limited | Some awareness | Enterprise-wide | Real-time |
| **External Participation** | Not understood | Understood | Collaborative | Leadership |
| **Consistency** | Inconsistent | Partial | Repeatable | Optimized |
| **Improvement** | Reactive | Irregular | Regular | Continuous |

---

## Online Resources dan Informative References

### CSF Online Resources

NIST menyediakan resources online untuk mendukung implementasi CSF:

#### 1. Informative References

**Apa itu?**
- Mapping dari CSF Subcategories ke kontrol spesifik dalam frameworks dan standards lain
- Membantu organisasi leverage existing investments

**Frameworks yang Di-Map:**
- **NIST SP 800-53 Rev 5**
- **ISO/IEC 27001**
- **CIS Controls**
- **COBIT**
- **ISA/IEC 62443** (Industrial Control Systems)
- Dan banyak lagi...

**Contoh Mapping:**
```
CSF Subcategory: PR.AA-1 (Identities dan credentials managed)
→ NIST SP 800-53r5: IA-2, IA-4, IA-5, IA-8
→ ISO 27001: A.9.2.1, A.9.2.2, A.9.2.4
→ CIS Controls: 5.1, 5.2, 5.3
```

**Manfaat:**
- Tidak perlu "mulai dari nol"
- Demonstrate compliance dengan multiple frameworks
- Leverage tools yang sudah ada

#### 2. Implementation Examples

**Apa itu?**
- Contoh konkret bagaimana organisasi dapat achieve subcategory outcomes
- Real-world scenarios

**Categories:**
- **Technology examples:** Specific products atau tools
- **Process examples:** Procedures dan workflows
- **People examples:** Training dan roles

#### 3. Quick Start Guides

**Apa itu?**
- Panduan untuk specific audiences atau use cases
- Simplified path untuk mulai dengan CSF

**Tersedia untuk:**
- Small businesses
- Manufacturing
- Healthcare
- Supply chain risk management

---

## Improving Cybersecurity Risk Communication and Integration

### Mengapa Komunikasi Penting?

> [!IMPORTANT]
> Salah satu nilai terbesar CSF adalah sebagai **common language** untuk komunikasi cybersecurity risk antar stakeholders dengan different backgrounds.

### Gap yang Dijembatani CSF

**Traditional Problem:**
```
┌─────────────────────────┐
│   Board / C-Suite       │ → "What's our cyber risk?"
│   (Business Language)   │ → "Are we compliant?"
└──────────┬──────────────┘
           │
           │  ❌ Communication Gap ❌
           │
┌──────────▼──────────────┐
│   Security Team         │ → "We need more firewalls"
│   (Technical Language)  │ → "Log4j vulnerability"
└─────────────────────────┘
```

**CSF Solution:**
```
┌─────────────────────────┐
│   Board / C-Suite       │
│   CSF Language:         │ → "Our IDENTIFY and PROTECT
│   Functions, Tiers      │    functions are Tier 3"
└──────────┬──────────────┘
           │
           │  ✅ Common Language ✅
           │
┌──────────▼──────────────┐
│   Security Team         │
│   CSF Language:         │ → "We're at 85% of Target
│   Subcategories,        │    Profile for PR.AA"
│   Implementation        │
└─────────────────────────┘
```

### Komunikasi dengan Executive Leadership

**CEO/Board:**
- **Use:** Functions dan Tiers
- **Focus:** Business risks, not technical details
- **Example:** "We've improved from Tier 2 to Tier 3 in our PROTECT function, reducing risk of data breaches by 40%"

**CFO:**
- **Use:** Cost-benefit dalam CSF terms
- **Focus:** ROI of cybersecurity investments
- **Example:** "Investing in DETECT capabilities (DE.CM) will reduce incident response costs by $500K annually"

**Legal/Compliance:**
- **Use:** Profiles mapped to regulations
- **Focus:** Compliance demonstrations
- **Example:** "Our Target Profile covers 95% of GDPR requirements through PR.DS dan GV.PO subcategories"

### Komunikasi dengan Technical Teams

**Security Team:**
- **Use:** Subcategories dan Implementation Examples
- **Focus:** Specific controls dan metrics
- **Example:** "Implement ID.RA-5 by deploying vulnerability scanner with weekly scans"

**IT Operations:**
- **Use:** Subcategories untuk daily operations
- **Focus:** Operational impact
- **Example:** "PR.IP-1 requires baseline configuration for all servers - update runbooks accordingly"

### Integrasi dengan Enterprise Risk Management (ERM)

**Cybersecurity as Business Risk:**

CSF 2.0 menekankan bahwa cybersecurity risk adalah **enterprise risk**, bukan hanya IT risk.

**GOVERN Function = Bridge ke ERM:**
```
┌─────────────────────────────────────────────┐
│     Enterprise Risk Management (ERM)        │
│  • Financial Risk                           │
│  • Operational Risk                         │
│  • Strategic Risk                           │
│  • Reputation Risk                          │
└──────────────────┬──────────────────────────┘
                   │
                   │  GV.RR: Integration
                   │
┌──────────────────▼──────────────────────────┐
│     Cybersecurity Risk (via CSF)            │
│  • GOVERN → Strategy Alignment              │
│  • IDENTIFY → Asset/Risk Awareness          │
│  • PROTECT, DETECT, RESPOND, RECOVER        │
└─────────────────────────────────────────────┘
```

**Benefits:**
- Holistic view of organizational risk
- Better resource allocation
- Executive understanding dan buy-in
- Regulatory compliance

---

## Implementasi CSF 2.0: Panduan Praktis

### Langkah 1: Prepare (Persiapan)

**Aktivitas:**
1. **Secure Executive Sponsorship**
   - Present CSF value proposition ke leadership
   - Obtain commitment dan resources

2. **Assemble Team**
   - Cross-functional: Security, IT, Business, Legal, Risk
   - Assign roles dan responsibilities

3. **Define Scope**
   - Entire organization atau specific business units?
   - Specific systems atau processes?

4. **Set Objectives**
   - Why implementing CSF?
   - What success looks like?

### Langkah 2: Create Current Profile

**Aktivitas:**
1. **Select Relevant Subcategories**
   - Review all 100+ subcategories
   - Pilih yang applicable ke scope

2. **Assess Current State**
   - Self-assessment atau third-party audit
   - Document implementation level

**Assessment Methods:**
- Interviews dengan stakeholders
- Document reviews
- Technical assessments
- Compliance audits

**Dokumentasi:**
```
Subcategory: PR.AA-1
Description: Identities dan credentials managed
Current State: Partially Implemented (60%)
Evidence:
  - MFA deployed untuk 60% users
  - Password policy exists but not enforced everywhere
  - Service accounts tidak fully managed
Notes: Gap di service account management
```

### Langkah 3: Create Target Profile

**Aktivitas:**
1. **Define Target State**
   - Based on risk appetite
   - Regulatory requirements
   - Industry best practices
   - Threat landscape

2. **Prioritize Outcomes**
   - Align dengan business objectives
   - Resource availability

3. **Set Timeline**
   - Realistic timeline untuk reach target
   - Phased approach

**Considerations:**
- Regulatory deadlines
- Budget cycles
- Technology refresh schedules
- Skill availability

### Langkah 4: Conduct Gap Analysis

**Aktivitas:**
1. **Compare Current vs Target**
   - Identify gaps untuk each subcategory
   - Quantify gaps (percentage, maturity level)

2. **Risk Assessment**
   - What risks do gaps create?
   - Likelihood dan impact

3. **Prioritization**
   - Rank gaps berdasarkan risk
   - Quick wins vs long-term improvements

**Gap Analysis Template:**
```
Subcategory: DE.CM-1 (Network monitored)
Current: 40% (Basic logging only)
Target: 90% (Full SIEM with alerting)
Gap: 50%
Risk: HIGH (Cannot detect advanced threats)
Priority: 1
Estimated Effort: 6 months, $200K
Dependencies: SIEM procurement, training
```

### Langkah 5: Develop Action Plan

**Aktivitas:**
1. **Create Implementation Roadmap**
   - Phases dan milestones
   - Dependencies

2. **Assign Ownership**
   - Who responsible untuk each action?
   - Accountability

3. **Resource Planning**
   - Budget
   - Personnel
   - Technology

4. **Risk Management**
   - What jika timeline slips?
   - Compensating controls

**Sample Roadmap:**
```
Phase 1 (Q1-Q2 2024): Foundation
  • Implement MFA (PR.AA)
  • Establish incident response plan (RS.MA)
  • Deploy basic monitoring (DE.CM)

Phase 2 (Q3-Q4 2024): Enhancement
  • Deploy SIEM (DE.CM, DE.AE)
  • Encryption at rest (PR.DS)
  • Supply chain assessment (GV.SC)

Phase 3 (Q1-Q2 2025): Optimization
  • Advanced threat detection (DE.CM)
  • Automated response (RS.MI)
  • Continuous monitoring (All functions)
```

### Langkah 6: Implement

**Aktivitas:**
1. **Execute Action Plan**
   - Follow roadmap
   - Track progress

2. **Monitor dan Report**
   - Regular status updates
   - Executive dashboards

3. **Manage Changes**
   - Adjust plan sebagai needed
   - Change control

**Success Factors:**
- ✅ Regular communication
- ✅ Quick wins untuk momentum
- ✅ Address resistance
- ✅ Training dan awareness

### Langkah 7: Monitor dan Improve

**Aktivitas:**
1. **Continuous Monitoring**
   - Track metrics
   - Progress terhadap Target Profile

2. **Periodic Reassessment**
   - Annual atau bi-annual
   - Update Current Profile

3. **Lessons Learned**
   - What worked? What didn't?
   - Incorporate improvements

4. **Adapt to Changes**
   - New threats
   - New regulations
   - Business changes
   - Technology evolution

**Metrics to Track:**
- % of Target Profile achieved
- Number of gaps closed
- Time to detect/respond incidents
- Investment ROI
- Compliance status

---

## CSF 2.0 dan Framework Lainnya

### Relationship dengan NIST SP 800-53

**NIST SP 800-53** adalah katalog detail kontrol keamanan.
**CSF** adalah high-level framework untuk risk management.

**Bagaimana Bekerja Bersama:**
```
CSF (Strategic)
  ↓
  PR.AA-1: Identities dan credentials managed
  ↓
  Map ke SP 800-53 (Tactical)
  ↓
  IA-2: Identification and Authentication
  IA-4: Identifier Management
  IA-5: Authenticator Management
```

**Use Case:**
- Use **CSF** untuk communicate dengan executives dan create roadmap
- Use **SP 800-53** untuk implement specific technical controls

### Relationship dengan ISO 27001

**ISO 27001** adalah international standard untuk Information Security Management System (ISMS).

**Similarities:**
- Risk-based approach
- Continuous improvement
- Management commitment

**Differences:**
- ISO 27001 adalah **certification standard**
- CSF adalah **voluntary framework**

**Complementary Use:**
- Achieve CSF outcomes → demonstrates many ISO 27001 requirements
- Informative References map CSF ke ISO controls

### Relationship dengan Zero Trust Architecture

**Zero Trust** adalah security model dan architectural approach.
**CSF** adalah risk management framework.

**How They Relate:**
```
CSF provides WHAT outcomes to achieve
  Example: PR.AA-1: Identity management

Zero Trust provides HOW to architect
  Example: Continuous verification, least privilege

Together:
  CSF defines risk-based priorities
  → Zero Trust implements architecture
  → Achieved cybersecurity outcomes
```

**Example:**
- **CSF Target:** PR.AA (Identity and Access Management) at Tier 3
- **ZTA Implementation:** Policy Engine, MFA, micro-segmentation
- **Result:** Strong access controls aligned dengan business risk

---

## Use Cases dan Contoh

### Use Case 1: Small E-Commerce Business

**Organization:** Online retailer, 50 employees, processes credit cards

**Starting Point:**
- No formal cybersecurity program
- Basic antivirus dan firewall
- Tier 1 (Partial)

**CSF Implementation:**

**Step 1: Prioritize Key Functions**
- **IDENTIFY:** Know what customer data exists
- **PROTECT:** PCI-DSS compliance for payment data
- **DETECT:** Monitor untuk fraud dan breaches

**Step 2: Target Profile (Tier 2)**
```
Priority Subcategories:
  ID.AM-5: Resources prioritized (customer data = critical)
  PR.DS-1: Data-at-rest protected (encrypt customer DB)
  PR.DS-2: Data-in-transit protected (HTTPS, TLS)
  DE.CM-1: Network monitored (basic IDS)
  RS.MA-1: Incident response plan exists
```

**Step 3: Implementation (12 months)**
- Month 1-3: Asset inventory, data classification
- Month 4-6: Encryption, access controls
- Month 7-9: Monitoring tools, IDS
- Month 10-12: Incident response plan, training

**Results:**
- PCI-DSS compliant
- Reduced fraud incidents by 70%
- Customer trust increased

### Use Case 2: Healthcare Provider

**Organization:** Hospital system, 5000 employees, HIPAA regulated

**Starting Point:**
- Existing security program (Tier 2)
- Recent ransomware scare
- Need to improve DETECT dan RESPOND

**CSF Implementation:**

**Step 1: Gap Analysis**
```
Function    Current  Target  Gap
GOVERN      Tier 2   Tier 3  Need better risk integration
IDENTIFY    Tier 3   Tier 3  ✓ Good
PROTECT     Tier 2   Tier 3  Patch management gaps
DETECT      Tier 1   Tier 3  Major gap - no SIEM
RESPOND     Tier 2   Tier 3  IR plan exists tapi tidak tested
RECOVER     Tier 2   Tier 3  Backup tetapi RTO unclear
```

**Step 2: Prioritized Actions**
1. **GOVERN:** Establish cybersecurity committee dengan C-suite representation
2. **DETECT:** Deploy SIEM untuk all critical systems
3. **RESPOND:** Test IR plan quarterly
4. **PROTECT:** Automated patch management

**Step 3: Implementation (18 months)**
- Q1: SIEM procurement dan deployment
- Q2: First IR tabletop exercise
- Q3: Patch automation untuk 80% systems
- Q4: Quarterly reporting ke Board
- Q5-Q6: Continuous improvement

**Results:**
- Detected dan contained ransomware attempt in 2 hours (vs days before)
- Board confidence increased
- HIPAA audit passed with zero findings

### Use Case 3: Manufacturing Company (OT/ICS)

**Organization:** Industrial manufacturer, mix of IT dan OT networks

**Starting Point:**
- IT network: Tier 2
- OT network: Tier 1 (legacy systems, little visibility)
- Concern: Industrial espionage, sabotage

**CSF Implementation:**

**Challenge:** OT systems have different requirements
- Can't patch frequently (production uptime)
- Can't install agents on PLCs
- Air-gapped networks

**Solution:** Use **CSF Profiles** untuk differentiate

**IT Network Target Profile:**
```
Standard CSF + emphasis on:
  PR.AA: Strong access controls
  DE.CM: Advanced monitoring
  Target: Tier 3
```

**OT Network Target Profile:**
```
Adapted CSF:
  PR.AC-5: Network segmentation (isolate OT)
  DE.CM-4: Alarms via passive monitoring
  RS.MA: OT-specific incident response
  Target: Tier 2 (appropriate untuk OT constraints)
```

**Implementation:**
- Network segmentation dengan DMZ antara IT-OT
- Passive monitoring (no agents)
- Jump boxes dengan multi-factor auth untuk OT access
- OT-aware IR plan

**Results:**
- Detected unauthorized access attempt ke OT network
- Zero production downtime dari security measures
- Compliance dengan IEC 62443

---

## Benefits dan Nilai CSF 2.0

### Untuk Organisasi

1. **Common Language**
   - ✅ Bridge communication gaps
   - ✅ Alignment across departments
   - ✅ Easier vendor conversations

2. **Risk-Based Approach**
   - ✅ Prioritize berdasarkan business impact
   - ✅ Efficient resource allocation
   - ✅ Cost-effective security

3. **Flexibility**
   - ✅ Applicable ke semua industries
   - ✅ Scalable untuk semua sizes
   - ✅ Technology dan vendor agnostic

4. **Demonstrate Due Diligence**
   - ✅ Show stakeholders cybersecurity is managed
   - ✅ Board reporting
   - ✅ Customer assurance

5. **Facilitate Compliance**
   - ✅ Map to multiple regulations
   - ✅ Streamline audits
   - ✅ Reduce compliance costs

### Untuk Ecosystem

1. **Supply Chain Risk Management**
   - ✅ Common expectations untuk vendors
   - ✅ Assessment criteria
   - ✅ Contractual requirements

2. **Information Sharing**
   - ✅ Common taxonomy untuk threat intel
   - ✅ Industry collaboration
   - ✅ Sector-specific initiatives

3. **Raise Security Bar**
   - ✅ Industry-wide improvements
   - ✅ Best practice dissemination
   - ✅ Collective defense

---

## Kesimpulan dan Next Steps

### Kesimpulan Utama

1. **CSF 2.0 = Major Evolution**
   - GOVERN function menjadikan framework lebih enterprise-oriented
   - Expanded audience beyond critical infrastructure
   - Enhanced integration dengan broader risk management

2. **Flexible dan Adaptable**
   - Bukan one-size-fits-all
   - Organizations dapat tailor to their needs
   - Applicable across sectors dan sizes

3. **Communication adalah Kunci**
   - Value terbesar: common language
   - Bridges technical-business gap
   - Enables risk-informed decisions

4. **Continuous Process**
   - Bukan one-time project
   - Ongoing assessment dan improvement
   - Adapt to evolving threats

### Recommended Next Steps

#### Untuk Organisasi yang Baru Mulai

1. **Learn dan Educate**
   - Read CSF 2.0 document
   - Training untuk key personnel
   - Executive briefing

2. **Start Simple**
   - Pilot dengan one business unit atau system
   - Create basic Current Profile
   - Identify top 5 gaps

3. **Quick Wins**
   - Implement low-hanging fruit
   - Show early value
   - Build momentum

#### Untuk Organisasi dengan CSF 1.1

1. **Understand Changes**
   - Review GOVERN function
   - Update Profiles dengan new subcategories
   - Consider expanded scope

2. **Reassess**
   - Update Current Profile
   - Revise Target Profile dengan GOVERN outcomes
   - New gap analysis

3. **Integrate GOVERN**
   - Establish governance processes
   - Connect cybersecurity ke ERM
   - Board engagement

### Resources

**Official NIST Resources:**
- CSF 2.0 Main Page: https://www.nist.gov/cyberframework
- Informative References Spreadsheet
- Quick Start Guides
- Implementation showcases

**Community Resources:**
- NIST Cybersecurity Framework workshops
- Industry sector working groups
- CSF user stories

---

## Glosarium

| Istilah | Penjelasan |
|---------|-----------|
| **CSF Core** | Set hasil cybersecurity yang terorganisir dalam Functions, Categories, Subcategories |
| **Function** | 6 high-level cybersecurity activities: GOVERN, IDENTIFY, PROTECT, DETECT, RESPOND, RECOVER |
| **Category** | 23 subdivisions dari Functions |
| **Subcategory** | 100+ specific outcomes dalam setiap Category |
| **Profile** | Customization dari CSF Core untuk kebutuhan spesifik organisasi |
| **Current Profile** | Status cybersecurity saat ini |
| **Target Profile** | Desired cybersecurity state |
| **Tier** | Karakterisasi tingkat keketatan manajemen cybersecurity risk (1-4) |
| **Informative References** | Mapping CSF ke frameworks dan standards lain |
| **Implementation Examples** | Contoh konkret bagaimana achieve outcomes |

---

**Catatan Penting:**

> [!TIP]
> CSF adalah **voluntary framework** - tidak ada yang "required". Organisasi memilih apa yang applicable dan valuable untuk mereka. Gunakan CSF sebagai tool, bukan checklist yang harus diikuti buta.

**Dokumen ini berdasarkan:** NIST Cybersecurity Framework (CSF) 2.0, CSWP 29 (26 Februari 2024)

**Untuk informasi terbaru, selalu rujuk ke:** https://www.nist.gov/cyberframework
