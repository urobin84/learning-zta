# Penjelasan NIST SP 800-63-3: Digital Identity Guidelines Implementation Resources

## Informasi Dokumen

**Judul Lengkap:** NIST Special Publication 800-63-3 Implementation Resources

**Tanggal Publikasi:** 1 Juli 2020

**Jumlah Halaman:** 82 halaman

**Tipe Dokumen:** Informative Implementation Guidance (Non-normative)

**Status:** Final

**Online Version:** https://pages.nist.gov/800-63-3-Implementation-Resources/

**Kata Kunci:** Digital Identity, Authentication, Identity Proofing, Federation, Assurance Levels, IAL, AAL, FAL

---

## Ringkasan Eksekutif

> [!IMPORTANT]
> NIST SP 800-63-3 Implementation Resources adalah **panduan praktis** untuk mengimplementasikan persyaratan normatif dari NIST SP 800-63-3 (Digital Identity Guidelines). Dokumen ini bersifat **informative** dan menyediakan guidance teknis, praktis, dan "how-to" untuk menerjemahkan persyaratan abstrak menjadi implementasi teknologi konkret.

**Hubungan dengan SP 800-63-3:**
- **SP 800-63-3** (suite utama) = Normative requirements (HARUS dipenuhi)
- **Implementation Resources** = How-to guidance (Panduan cara implementasi)

---

## Apa itu NIST SP 800-63-3?

### Overview SP 800-63-3 Suite

NIST Special Publication 800-63-3 adalah **Digital Identity Guidelines** yang terdiri dari empat volume:

| Volume | Nama | Fokus |
|--------|------|-------|
| **SP 800-63-3** | Digital Identity Guidelines | Overview dan model umum |
| **SP 800-63A** | Enrollment and Identity Proofing | Identity Assurance Levels (IAL) |
| **SP 800-63B** | Authentication and Lifecycle Management | Authenticator Assurance Levels (AAL) |
| **SP 800-63C** | Federation and Assertions | Federation Assurance Levels (FAL) |

### Mengapa Digital Identity Penting?

**Digital Identity** adalah representasi online dari subject (person atau non-person entity) yang digunakan dalam transaksi elektronik.

**Tantangan:**
- Bagaimana memastikan user adalah siapa yang mereka klaim?
- Berapa banyak verifikasi yang diperlukan?
- Bagaimana balance antara security, privacy, dan usability?

**Solusi NIST:**
- **Risk-based approach:** Pilih level assurance berdasarkan impact
- **Modular framework:** IAL, AAL, FAL dapat dipilih independently
- **Privacy-focused:** Minimisasi PII collection

---

## Struktur Implementation Resources

Dokumen Implementation Resources dibagi menjadi tiga bagian utama:

### Part A: SP 800-63A Implementation (Identity Proofing)

**Fokus:** Bagaimana memverifikasi bahwa seseorang adalah siapa yang mereka klaim
- Enrollment processes
- Identity proofing phases
- Identity Assurance Levels (IAL)

### Part B: SP 800-63B Implementation (Authentication)

**Fokus:** Bagaimana memverifikasi bahwa user adalah pemilik sah dari credential
- Authentication methods
- Authenticator types
- Authenticator Assurance Levels (AAL)

### Part C: SP 800-63C Implementation (Federation)

**Fokus:** Bagaimana share identity information across systems secara aman
- Federation protocols (SAML, OIDC, OAuth)
- Assertions
- Federation Assurance Levels (FAL)

---

## Part A: Identity Proofing dan IAL

### Konsep Dasar Identity Proofing

**Identity Proofing** adalah proses untuk mengumpulkan, memvalidasi, dan memverifikasi informasi tentang seseorang agar dapat meng-establish valid identity.

**Tujuan:**
- Ensure bahwa identity yang di-claim adalah real
- Bind digital identity ke real-world person
- Mencegah fraud dan identity theft

### Tiga Tahap Identity Proofing

#### 1. Resolution (Resolusi)

**Definisi:** Identifikasi **unique individual** dalam konteks populasi tertentu.

**Tujuan:**
- Distinguish one person dari yang lain
- Prevent identity dapat di-claim oleh multiple people

**How to Achieve:**
- Kumpulkan **core attributes:** nama, tanggal lahir, alamat
- Attributes harus cukup untuk uniquely identify
- Correlation dengan existing records

**Contoh:**
```
Input: John Smith, DOB: 01/01/1980, Address: 123 Main St
→ Resolved to unique record in database
→ NOT confused dengan John Smith, DOB: 01/01/1982
```

**Common Failures:**
- Attributes tidak cukup untuk distinguish (nama terlalu umum)
- Data quality issues (typos, outdated)
- Loss of attribute correlation

#### 2. Validation (Validasi)

**Definisi:** Evidence yang dilampirkan oleh applicant harus **legitimate dan current**.

**Tujuan:**
- Ensure identity evidence (ID card, passport) adalah real, bukan fake
- Verify evidence belum expired atau revoked

**Methods:**
- **Document verification:** Check security features, barcodes, holograms
- **Record verification:** Cross-check dengan issuing authority
- **Data consistency:** Information matches across sources

**Contoh Evidence:**
- **SUPERIOR:** Passport, driver's license dengan crypto verification
- **STRONG:** Utility bill, bank statement
- **FAIR:** School ID, social media verification (dengan limitations)

**Common Failures:**
- Fake documents
- Expired evidence
- Evidence tidak match dengan claimed identity

#### 3. Verification (Verifikasi)

**Definisi:** Confirm bahwa applicant adalah **rightful owner** dari validated identity.

**Tujuan:**
- Bind identity ke real person yang sedang enroll
- Prevent seseorang menggunakan identity orang lain

**Methods:**
- **In-person:** Physical comparison, biometrics
- **Remote:** Knowledge-based verification (KBV), out-of-band verification
- **Biometric comparison:** Selfie vs photo on ID

**Contoh:**
```
Applicant submits driver's license
→ Validation: License adalah valid dan current ✓
→ Verification: Selfie match dengan photo di license ✓
→ Identity binding confirmed
```

**Common Failures:**
- Biometric tidak match
- KBV questions answered incorrectly
- Presentation attack (spoofed biometrics)

### Identity Assurance Levels (IAL)

> [!NOTE]
> IAL adalah tingkat **confidence** bahwa identity yang di-claimed oleh applicant adalah identity sebenarnya.

#### IAL1: No Identity Proofing Required

**Karakteristik:**
- **No requirement** untuk link user ke specific real-life identity
- Self-asserted attributes saja
- Suitable untuk low-risk transactions

**Use Cases:**
- Membaca public information
- Newsletter subscriptions
- Anonymous forums
- Low-value retail

**Attributes:**
- Dapat sepenuhnya pseudonymous
- Email address mungkin cukup
- Tidak ada validation terhadap real-world identity

**Example:**
```
User Registration:
  - Username: user123
  - Email: user@email.com (verified dengan link)
  - No real name required
  
→ IAL1: Identity tidak di-proofed
```

#### IAL2: Identity Proofing Required

**Karakteristik:**
- Identity proofing **required**
- Evidence harus di-validated
- Remote atau in-person proofing
- Support untuk pseudonymous use

**Requirements:**
- Resolution ke unique individual
- Validation of evidence dengan **STRONG atau SUPERIOR** source
- Verification bahwa applicant adalah owner of identity

**Use Cases:**
- Healthcare portal access
- Financial services account
- Government services (moderate risk)
- Employment verification

**Process:**
```
1. Collect attributes: Name, DOB, SSN, Address
2. Validate evidence: Driver's license verified
3. Remote verification: 
   - Knowledge-Based Verification (KBV) questions
   - OR Out-of-Band (OOB) confirmation ke phone
4. Enroll authenticator
```

**Example:**
```
Bank Account Opening (Remote):
  1. Submit driver's license photo
  2. Take selfie untuk biometric comparison
  3. Answer KBV questions based on credit history
  4. Confirm via SMS ke registered phone
  
→ IAL2: Identity proofed to real person
```

#### IAL3: In-Person Identity Proofing Required

**Karakteristik:**
- **In-person** atau supervised remote proofing
- Highest level of assurance
- Biometric collection
- Cryptographic binding

**Requirements:**
- Presence di authorized location ATAU supervised remote session
- **SUPERIOR** identity evidence
- Biometric capture untuk future verification
- Background checks (may be required)

**Use Cases:**
- Military/government employees
- Law enforcement
- High-value financial transactions
- Controlled substance prescribing

**Process:**
```
1. In-person appearance di enrollment station
2. Present passport atau state-issued ID
3. Trained agent verifies security features
4. Biometric capture: fingerprint, iris scan
5. Live detection (ensure not photo/video)
6. Background check (jika diperlukan)
7. Enroll cryptographic hardware token
```

**Example:**
```
Government Credential (PIV Card):
  1. Applicant appears in-person at federal building
  2. HR verifies employment authorization
  3. Presents passport dan second ID
  4. Fingerprints captured dan checked against database
  5. Photo taken dengan live detection
  6. PIV card issued dengan PKI certificate
  
→ IAL3: Highest assurance identity
```

### IAL Comparison Table

| Aspek | IAL1 | IAL2 | IAL3 |
|-------|------|------|------|
| **Identity Proofing** | None | Required | Required |
| **Evidence** | Self-asserted | STRONG/SUPERIOR | SUPERIOR only |
| **Validation** | None | Validated dari sources | Validated + verified |
| **Verification** | None | Remote methods | In-person atau supervised |
| **Biometrics** | Not collected | Optional | Required |
| **Binding** | None | Digital binding | Cryptographic binding |
| **Privacy** | Fully pseudonymous | Can be pseudonymous | Real identity required |

---

## Part B: Authentication dan AAL

### Konsep Dasar Authentication

**Authentication** adalah proses verifikasi bahwa **claimant** controls authenticator(s) yang bound ke subscriber account.

**Key Terms:**
- **Claimant:** Person atau entity yang claiming identity
- **Authenticator:** Something yang proves identity (password, token, biometric)
- **Credential:** Binding antara authenticator dan subscriber identity
- **Verifier:** System yang verifies authenticator

### Authenticator Types

#### 1. Memorized Secret (Password)

**Deskripsi:** Something you **know**

**Characteristics:**
- Shared secret antara subscriber dan verifier
- Chosen oleh subscriber atau assigned

**Requirements (NIST):**
- Minimal 8 characters jika user-chosen
- Minimal 6 characters jika random-generated
- No complexity requirements (no forced special chars)
- Check against common password lists
- Allow paste (untuk password managers)

**Strengths:**
- ✅ Familiar untuk users
- ✅ No special hardware
- ✅ Easy untuk recover

**Weaknesses:**
- ❌ Can be guessed, phished
- ❌ Often reused across sites
- ❌ Vulnerable ke database breaches

#### 2. Look-Up Secrets

**Deskripsi:** Pre-registered secrets yang looked up oleh claimant

**Examples:**
- Recovery codes (printed list)
- Scratch-off cards dengan codes

**Characteristics:**
- Physical atau electronic list
- One-time use (typically)

**Strengths:**
- ✅ Simple
- ✅ Offline capability

**Weaknesses:**
- ❌ Can be lost atau stolen
- ❌ Limited usage (deplete over time)

#### 3. Out-of-Band (OOB) Devices

**Deskripsi:** Secondary channel untuk authentication

**Examples:**
- SMS dengan verification code
- Voice call dengan code
- Push notification ke mobile app

**Characteristics:**
- Separate channel dari primary session
- Time-limited codes

**Strengths:**
- ✅ Proof of device possession
- ✅ Intuitive untuk users

**Weaknesses:**
- ❌ SMS can be intercepted (SIM swap)
- ❌ Depends on network availability
- ❌ Channel may not be truly independent

> [!WARNING]
> SMS OOB is **restricted** oleh NIST. Preferred: dedicated authenticator apps atau push notifications.

#### 4. Single-Factor OTP Device

**Deskripsi:** Generate one-time passwords

**Examples:**
- Hardware token (RSA SecurID)
- Software TOTP app (Google Authenticator, Authy)

**How it Works:**
```
Shared secret + Time/Counter
    ↓
Algorithm (TOTP/HOTP)
    ↓
6-8 digit code (changes setiap 30s untuk TOTP)
```

**Strengths:**
- ✅ Time-bound codes (replay protection)
- ✅ No network required (TOTP)
- ✅ Widely supported

**Weaknesses:**
- ❌ Clock sync issues (TOTP)
- ❌ Phishable (code can be typed into fake site)
- ❌ Device can be lost/stolen

#### 5. Multi-Factor OTP Device

**Deskripsi:** OTP device dengan activation requirement

**Examples:**
- Hardware token yang requires PIN
- Software authenticator dengan biometric unlock

**Characteristics:**
- Combines "something you have" + "something you know/are"

**Strengths:**
- ✅ Stronger than single-factor OTP
- ✅ Mitigates theft scenarios

**Weaknesses:**
- ❌ Still phishable
- ❌ More complex untuk users

#### 6. Single-Factor Cryptographic Software

**Deskripsi:** Software-based private key

**Examples:**
- Software PKI certificates
- SSH keys stored di file system

**How it Works:**
```
Private key stored securely
    ↓
Challenge from verifier
    ↓
Sign challenge dengan private key
    ↓
Verifier checks signature dengan public key
```

**Strengths:**
- ✅ Strong cryptographic protection
- ✅ No shared secrets
- ✅ Scales well

**Weaknesses:**
- ❌ Key can be copied
- ❌ Vulnerable jika device compromised
- ❌ No authentication intent

#### 7. Single-Factor Cryptographic Device

**Deskripsi:** Hardware yang contains private key

**Examples:**
- Smart cards
- USB security keys (without user activation)
- TPM-bound keys

**Characteristics:**
- Private key **cannot leave** device
- Challenge-response via hardware

**Strengths:**
- ✅ Key cannot be extracted
- ✅ Hardware tamper resistance
- ✅ Strong assurance

**Weaknesses:**
- ❌ Device can be stolen dan used
- ❌ Cost of hardware

#### 8. Multi-Factor Cryptographic Software

**Deskripsi:** Software crypto dengan activation factor

**Examples:**
- PKI certificate dengan password protection
- Mobile app signing dengan biometric

**Characteristics:**
- Software key + unlock mechanism

**Strengths:**
- ✅ Multi-factor protection
- ✅ No special hardware

**Weaknesses:**
- ❌ Software key still copyable
- ❌ Vulnerable ke malware

#### 9. Multi-Factor Cryptographic Device

**Deskripsi:** Hardware crypto dengan activation factor

**Examples:**
- PIV/CAC smart card dengan PIN
- FIDO2 security key dengan biometric/PIN
- U2F keys (YubiKey, Titan)

**How it Works:**
```
User inserts/connects device
    ↓
User authenticates (PIN or biometric)
    ↓
Device performs cryptographic operation
    ↓
Response sent tanpa exposing key
```

**Strengths:**
- ✅ Highest security
- ✅ Phishing-resistant (FIDO2)
- ✅ Authentication intent (user action)
- ✅ Key bound ke hardware

**Weaknesses:**
- ❌ Cost
- ❌ Can be lost (mitigated dengan backup)
- ❌ User complexity (sometimes)

### Authenticator Assurance Levels (AAL)

> [!NOTE]
> AAL adalah tingkat **confidence** bahwa claimant controls authenticator(s) yang bound ke subscriber identity. AAL adalah property dari **authentication session**, bukan authenticator itu sendiri.

#### AAL1: Single-Factor Authentication

**Requirements:**
- Wide range of authenticator types accepted
- **Minimal:** Memorized secret (password)
- OR any single-factor authenticator

**Allowed Authenticators:**
- Memorized Secret
- Look-Up Secret
- Out-of-Band (dengan restrictions)
- Single-Factor OTP
- Single-Factor Crypto (software atau device)

**Appropriate untuk:**
- Low-risk transactions
- Public information access
- Basic services

**Example:**
```
Login dengan username + password
→ AAL1
```

**NOT Allowed:**
- Biometrics alone (must be bound to device/software)

#### AAL2: Multi-Factor Authentication (MFA)

**Requirements:**
- **Two different factors** dari:
  - Something you know (knowledge)
  - Something you have (possession)
  - Something you are (inherence/biometrics)
- Replay resistance
- FIPS 140 Level 1 untuk government authenticators

**Allowed Combinations:**
- Memorized Secret + OOB Device
- Memorized Secret + Single-Factor OTP
- Multi-Factor OTP Device
- Multi-Factor Crypto Software
- Single-Factor Crypto Device + Memorized Secret

**Key Requirement: Replay Resistance**
- Session hijacking protection
- Eavesdropping protection

**Appropriate untuk:**
- Moderate-risk transactions
- PII access
- Financial services
- Healthcare data

**Examples:**
```
Example 1: Password + SMS OTP
→ AAL2 (something you know + something you have)

Example 2: Password + Authenticator App (TOTP)
→ AAL2 (knowledge + possession)

Example 3: Smart Card + PIN
→ AAL2 (possession + knowledge)
```

#### AAL3: Multi-Factor Cryptographic Device

**Requirements:**
- **Hardware-based** multi-factor cryptographic device
- **Verifier impersonation resistance** (phishing-resistant)
- **Verifier compromise resistance**
- **Authentication intent** (user action required)
- FIPS 140 Level 2 atau higher untuk government

**Required Authenticator:**
- Multi-Factor Cryptographic **Device** only
  - PIV card dengan PIN
  - FIDO2 security key dengan biometric/PIN

**Key Properties:**

**1. Verifier Impersonation Resistance (Anti-Phishing):**
```
Attacker creates fake site with lookalike URL
→ FIDO2 key checks origin (cryptographically)
→ Origin doesn't match enrolled site
→ Key refuses to authenticate
→ User CANNOT be phished
```

**2. Verifier Compromise Resistance:**
- Even jika server database breached, attackers cannot impersonate users
- No shared secrets stored on server
- Public key infrastructure

**3. Authentication Intent:**
- User must perform intentional action (press button, biometric scan)
- Prevents "drive-by" authentication attacks
- Ensures user awareness

**Appropriate untuk:**
- High-risk transactions
- Privileged access
- Classified information
- High-value financial transactions

**Example:**
```
Login dengan FIDO2 Security Key:
  1. User navigates to site
  2. Inserts security key
  3. Presses button (authentication intent)
  4. Key verifies origin (anti-phishing)
  5. Key performs crypto operation dengan PIN/biometric
  6. Authentication succeeds
  
→ AAL3 (hardware MFA, phishing-resistant)
```

### AAL Comparison Table

| Aspek | AAL1 | AAL2 | AAL3 |
|-------|------|------|------|
| **Factors** | Single | Multi | Multi |
| **Authenticator** | Any (except biometric alone) | MFA combinations | Crypto device only |
| **Replay Protection** | Not required | Required | Required |
| **Phishing Resistant** | No | No | **Yes** |
| **Verifier Compromise** | Vulnerable | Vulnerable | **Resistant** |
| **Hardware Required** | No | No | **Yes** |
| **FIPS 140 (Gov)** | Optional | Level 1 | Level 2+ |
| **Use Case** | Low risk | Moderate risk | High risk |

---

## Part C: Federation dan FAL

### Konsep Dasar Federation

**Federation** adalah proces di mana **Identity Provider (IdP)** assert identity information tentang subscriber kepada **Relying Party (RP)** secara elektronik.

**Why Federation?**
- Reduce password sprawl (tidak perlu account di setiap service)
- Centralized identity management
- Single Sign-On (SSO)
- Privacy preservation (IdP can limit data shared)

**Key Roles:**
```
┌─────────────┐
│   Subject   │ (User)
└──────┬──────┘
       │
       │ 1. Authenticates to
       ▼
┌──────────────────────┐
│  Identity Provider   │
│      (IdP/CSP)       │
│  • Manages identity  │
│  • Authenticates     │
│  • Issues assertions │
└──────┬───────────────┘
       │
       │ 2. Assertion
       │
       ▼
┌──────────────────────┐
│   Relying Party     │
│       (RP)           │
│  • Trusts IdP        │
│  • Consumes assertion│
│  • Grants access     │
└──────────────────────┘
```

### Assertion

**Assertion** adalah statement dari IdP ke RP tentang subscriber.

**Contains:**
- Subject identifier (who the user is)
- Attributes (email, role, permissions)
- Authentication event details (when, how)
- Validity period

**Types:**
- **Bearer Assertion:** Possession adalah proof (like cash)
- **Holder-of-Key Assertion:** Must prove possession of private key

### Federation Protocols

#### SAML (Security Assertion Markup Language)

**Characteristics:**
- XML-based
- Mature, widely deployed
- Support untuk complex attributes
- Web browser SSO

**Use Case:**
```
Employee logs in dengan corporate AD
→ Accesses cloud SaaS application
→ SAML assertion contains groups, email
→ SaaS app grants access based on groups
```

**Example Flow:**
```
1. User attempts access to RP
2. RP redirects to IdP dengan SAML request
3. User authenticates di IdP
4. IdP generates SAML assertion (signed XML)
5. Assertion redirected back ke RP
6. RP validates signature dan grants access
```

#### OpenID Connect (OIDC)

**Characteristics:**
- JSON-based (JWT tokens)
- Built on OAuth 2.0
- Modern, RESTful
- Mobile-friendly

**Tokens:**
- **ID Token:** Identity information (sebagai JWT)
- **Access Token:** Authorization untuk API calls

**Use Case:**
```
User logs in "using Google"
→ Google adalah IdP
→ App (RP) receives ID token dengan email, name
→ App creates local account atau uses for SSO
```

**Example Flow:**
```
1. User clicks "Login with Google"
2. Redirected to Google (IdP)
3. User authenticates (if not already)
4. Google asks for consent (share email, profile?)
5. User approves
6. Google redirects back dengan authorization code
7. RP exchanges code for ID token + access token
8. RP validates ID token (signature, issuer, expiry)
9. RP extracts user info dari token
10. User logged in
```

#### OAuth 2.0

**Note:** OAuth is **authorization** framework, bukan authentication
- Often confused dengan OIDC
- OAuth grants **access** ke resources
- OIDC adds **identity** layer on top

### Federation Assurance Levels (FAL)

> [!NOTE]
> FAL adalah level of assurance bahwa assertion itu sendiri aman - confidentiality, integrity, dan authenticity yang dijaga selama federation process.

#### FAL1: Basic Federation

**Requirements:**
- Bearer assertions
- Assertion signed oleh IdP
- TLS protection untuk transmission

**Characteristics:**
- Assertion dapat di-intercept dan replayed (within validity)
- Suitable untuk low-risk scenarios

**Appropriate untuk:**
- Public information dengan login
- Low-value transactions
- Basic personalization

**Example:**
```
SAML assertion over HTTPS
→ Signed untuk integrity
→ No additional binding
→ FAL1
```

#### FAL2: Encrypted Assertion atau Holder-of-Key

**Requirements:**
- **EITHER:**
  - Assertion encrypted untuk RP (confidentiality)
  - **OR** Holder-of-Key mechanism (cannot replay)
- Assertion signed
- TLS still required

**Characteristics:**
- Protection against eavesdropping (encrypted)
- OR protection against replay (holder-of-key)

**Holder-of-Key:**
```
Assertion contains reference ke user's public key
→ RP challenges user untuk prove possession of private key
→ User must cryptographically respond
→ Prevents replay even jika assertion stolen
```

**Appropriate untuk:**
- Moderate-risk transactions
- PII in assertions
- Financial data access

**Example:**
```
OpenID Connect dengan encrypted ID token
→ Token encrypted untuk RP's public key
→ Only RP can decrypt
→ FAL2
```

#### FAL3: Cryptographic Proof of Possession

**Requirements:**
- Holder-of-Key mechanism **required**
- Assertion signed dan encrypted
- Key at AAL2 atau higher
- Presented directly ke RP (back channel) atau front channel dengan protections

**Characteristics:**
- Highest assurance
- Cannot replay assertion
- Strong binding antara subject dan assertion

**Appropriate untuk:**
- High-risk transactions
- Privileged access
- Sensitive data

**Example:**
```
PIV card dengan SAML:
  1. User authenticates to IdP dengan PIV (AAL3)
  2. IdP issues SAML assertion (signed + encrypted)
  3. Assertion contains reference ke PIV certificate
  4. RP challenges user untuk prove possession of PIV
  5. PIV performs cryptographic operation
  6. RP validates response
  
→ FAL3 (holder-of-key dengan AAL3 authenticator)
```

### FAL Comparison Table

| Aspek | FAL1 | FAL2 | FAL3 |
|-------|------|------|------|
| **Assertion Protection** | Signed | Signed + Encrypted OR HoK | Signed + Encrypted + HoK |
| **Confidentiality** | TLS only | Encrypted assertion | Encrypted assertion |
| **Replay Resistance** | Limited (time-based) | Enhanced | **Strong (HoK)** |
| **Complexity** | Low | Moderate | High |
| **Use Case** | Low risk | Moderate risk | High risk |

### Privacy in Federation

**Privacy Considerations:**

1. **Minimize Attributes Shared**
   - Only share what RP needs
   - Pseudonymous identifiers jika possible
   - User consent untuk attribute release

2. **Pairwise Pseudonymous Identifiers**
   - Different identifier untuk each RP
   - Prevents correlation across services
   - IdP can still map back ke real identity

**Example:**
```
User identity di IdP: john.doe@company.com

Assertions to different RPs:
  RP1 (Email service): uuid-12345abc
  RP2 (Calendar):      uuid-67890def
  RP3 (HR system):     uuid-abcde123

→ Each RP cannot correlate user across services
→ IdP maintains mapping untuk compliance/support
```

3. **Blinding**
   - IdP tidak tahu resources apa yang user access di RP
   - RP tidak tahu siapa IdP (dalam advanced scenarios)

---

## Kombinasi xAL: IAL, AAL, FAL

### Independent Selection

> [!TIP]
> Organizational penting: **IAL, AAL, dan FAL dapat dipilih independently** berdasarkan risk assessment untuk specific transaction.

**Why Independent?**
- Different risks untuk different aspects
- Flexibility untuk balance security dan usability
- Cost optimization

### Common Combinations

#### Combination 1: IAL2, AAL2, FAL1

**Scenario:** Healthcare Portal

**Rationale:**
- **IAL2:** Need untuk know real identity (untuk medical records)
- **AAL2:** Moderate authentication strength (MFA)
- **FAL1:** Basic federation (internal SSO dengan low risk)

**Implementation:**
```
Identity Proofing: Remote dengan driver's license + KBV
Authentication: Password + TOTP app
Federation: SAML over TLS (internal federation)
```

#### Combination 2: IAL1, AAL3, FAL2

**Scenario:** Anonymous Whistleblower Portal

**Rationale:**
- **IAL1:** Identity privacy preserved (no real name needed)
- **AAL3:** High authentication assurance (prevent impersonation)
- **FAL2:** Secure assertion (encrypted)

**Implementation:**
```
Identity Proofing: None (self-asserted pseudonym)
Authentication: FIDO2 security key với PIN
Federation: OpenID Connect dengan encrypted tokens
```

#### Combination 3: IAL3, AAL3, FAL3

**Scenario:** Top Secret Government System

**Rationale:**
- **IAL3:** Highest identity assurance (background check)
- **AAL3:** Phishing-resistant MFA (hardware)
- **FAL3:** Holder-of-Key (cannot replay)

**Implementation:**
```
Identity Proofing: In-person dengan biometrics, background check
Authentication: PIV card dengan PIN
Federation: SAML dengan holder-of-key assertion
```

### Selection Matrix

**Questions untuk ask:**

| Question | Determines |
|----------|-----------|
| Apa risk jika wrong person enrolled? | **IAL** |
| Apa risk jika account hacker takeover? | **AAL** |
| Apa risk jika assertion intercepted? | **FAL** |

**Decision Factors:**

**IAL Selection:**
- Apakah real identity required?
- Apa impact dari identity fraud?
- Privacy requirements?

**AAL Selection:**
- Apa value dari account?
- Apa impact dari unauthorized access?
- User population capabilities?

**FAL Selection:**
- Apa sensitivity dari attributes?
- Apakah replay attack possible?
- Network security posture?

---

## Implementation Scenarios dan Examples

### Scenario 1: E-Commerce Website (Low Risk)

**Use Case:** Public shopping site

**Requirements:**
- Allow browsing tanpa login
- Checkout requires account untuk shipping
- Low-value transactions (<$100)

**xAL Selection:**
```
IAL: IAL1 (no identity proofing)
  → Email address verification saja
  → Self-asserted name dan shipping address

AAL: AAL1 (password authentication)
  → Username + password
  → Optional social login (Google, Facebook)

FAL: N/A (no federation, atau FAL1 untuk social login)
```

**Implementation:**
```
Registration:
  - Email + Password
  - Email verification link

Login:
  - Username/Email + Password
  - Rate limiting untuk brute force protection
  - Optional: "Login dengan Google" (OIDC, FAL1)
```

**Why This Works:**
- Low risk of fraud
- Simple user experience
- Low implementation cost
- Scales well

### Scenario 2: Online Banking (Moderate-High Risk)

**Use Case:** Retail bank digital banking

**Requirements:**
- Real identity required (KYC/AML compliance)
- Protect financial data
- Enable high-value transactions

**xAL Selection:**
```
IAL: IAL2 (remote identity proofing)
  → Driver's license validation
  → Knowledge-based verification
  → OR in-branch enrollment

AAL: AAL2 (multi-factor authentication)
  → Password + SMS OTP
  → OR Password + Authenticator app
  → OR Password + Hardware token

FAL: N/A (no federation)
  → Bank manages identity directly
```

**Implementation:**
```
Account Opening:
  1. Submit personal information
  2. Upload driver's license photos
  3. Selfie untuk biometric match
  4. Answer KBV questions dari credit bureau
  5. Micro-deposit verification (bank account ownership)

Authentication:
  1. Username + Password
  2. SMS OTP ke registered phone
  3. Device fingerprinting (risk-based step-up)

High-Value Transactions (Step-Up):
  → Additional authentication untuk transfers >$5000
  → Challenge questions atau additional OTP
```

**Why This Works:**
- Meets regulatory requirements (KYC)
- Balances security dan user experience
- Remote enrollment (customer convenience)
- Fraud prevention

### Scenario 3: Federal Employee Access (High Risk)

**Use Case:** Access to government systems

**Requirements:**
- Highest identity assurance
- Phishing-resistant authentication
- Compliance dengan federal mandates

**xAL Selection:**
```
IAL: IAL3 (in-person proofing)
  → Background investigation
  → Biometric enrollment
  → Fingerprint check against FBI database

AAL: AAL3 (hardware MFA)
  → PIV card dengan PIN
  → OR FIDO2 security key dengan biometric

FAL: FAL3 (holder-of-key)
  → SAML dengan HoK
  → Secure federation across agencies
```

**Implementation:**
```
Onboarding:
  1. HR verifies employment authorization
  2. In-person appearance di federal facility
  3. Present passport + state ID
  4. Fingerprints captured
  5. FBI background check
  6. Photo taken dengan liveness detection
  7. PIV card issued dengan PKI certificate

Daily Authentication:
  1. Insert PIV card
  2. Enter PIN
  3. Certificate-based authentication
  4. Access granted ke workstation

Federated Access to Other Agency:
  1. User already authenticated dengan PIV
  2. Access cross-agency application
  3. SAML assertion generated
  4. Assertion contains reference ke PIV cert
  5. Receiving agency challenges untuk crypto proof
  6. PIV performs operation
  7. Access granted
```

**Why This Works:**
- Meets federal security requirements
- Phishing-resistant (PIV/FIDO2)
- Interoperable across agencies
- Audit trail

### Scenario 4: Healthcare Portal dengan Federation (Moderate Risk)

**Use Case:** Patient access to medical records via SSO

**Requirements:**
- Real identity (untuk link ke medical records)
- Federation dari multiple IdPs (employer, insurance)
- Privacy protection (HIPAA)

**xAL Selection:**
```
IAL: IAL2 (identity proofed di enrollment)
  → Remote proofing dengan ID + KBV
  → OR in-person di clinic

AAL: AAL2 (MFA)
  → Password + Authenticator app
  → OR Password + SMS OTP

FAL: FAL2 (encrypted assertions)
  → OpenID Connect dengan encrypted tokens
  → Minimize PII in assertions
```

**Implementation:**
```
Enrollment (via Hospital):
  1. New patient intake
  2. Present driver's license
  3. Staff verifies identity
  4. Create account dengan email verification
  5. Setup MFA

Federation (via Employer IdP):
  1. Employee logs in to employer portal (AAL2)
  2. Clicks link to health benefits
  3. Redirected to healthcare portal (RP)
  4. Employer IdP issues OIDC assertion
  5. Assertion encrypted untuk healthcare portal
  6. Contains: employee ID (pseudonymous), email
  7. Healthcare portal matches ke patient record
  8. Access granted to medical records

Privacy Protections:
  → Employer doesn't know what records accessed
  → Healthcare portal uses pairwise identifier
  → Audit logs untuk compliance
```

**Why This Works:**
- HIPAA compliance (identity verification)
- User convenience (SSO dari employer)
- Privacy preserved (minimal attributes)
- Secure federation (encrypted)

---

## Best Practices dan Recommendations

### For Identity Proofing (IAL)

1. **Document Your Process**
   - Create practice statement
   - Define acceptable evidence
   - Train enrollment staff

2. **Multiple Evidence Sources**
   - Cross-validate dari independent sources
   - Reduce single point of failure

3. **Privacy Preserving**
   - Collect minimum necessary untuk IAL
   - Offer pseudonymous options jika appropriate
   - Secure storage of PII

4. **Accessibility**
   - Provide alternative proofing methods
   - Accommodate disabilities
   - Multiple language support

### For Authentication (AAL)

1. **Enforce Password Quality**
   - Check against breach databases
   - Minimum 8 characters
   - No complexity requirements (NIST guidance)
   - Allow passphrases

2. **Implement MFA Smartly**
   - Default to AAL2 untuk most services
   - Avoid SMS jika possible (prefer authenticator apps)
   - Provide backup methods

3. **Plan for AAL3**
   - Invest di FIDO2 infrastructure
   - Phishing resistance adalah key value
   - Hardware tokens untuk high-value users

4. **Account Recovery**
   - Secure recovery process (don't undermine AAL)
   - Multiple options (security questions, backup codes, support)
   - Fraud checks

### For Federation (FAL)

1. **Choose Right Protocol**
   - OIDC untuk modern apps (mobile, API-driven)
   - SAML untuk enterprise SSO
   - Evaluate ecosystem support

2. **Minimize Attribute Sharing**
   - Principle of least privilege
   - User consent mechanisms
   - Attribute release policies

3. **Secure Assertions**
   - Always sign assertions
   - Encrypt sensitive attributes (FAL2+)
   - Short validity periods

4. **Test Federation Flows**
   - Simulate attacks (MITM, replay)
   - Validate signatures correctly
   - Monitor untuk anomalies

### Risk-Based Authentication

**Adaptive Authentication:**
- Monitor context signals (location, device, behavior)
- Step-up authentication untuk risky scenarios
- Lower friction untuk trusted context

**Example:**
```
User logs in dari known device, usual location
→ Username + password (AAL1)
→ Low friction

User logs in dari new country, new device
→ Username + password + OTP (step-up to AAL2)
→ Additional verification

High-value transaction requested
→ Additional challenge even jika already AAL2
→ Re-authentication atau secondary approval
```

---

## Common Pitfalls dan How to Avoid

### Pitfall 1: Confusing IAL dan AAL

**Problem:**
"User logged in dengan strong password, jadi kita punya high assurance identity"

**Reality:**
- Strong authentication (AAL) ≠ Verified identity (IAL)
- AAL confirms user controls credential
- IAL confirms credential bound to real person

**Solution:**
- Assess IAL dan AAL separately
- Document risk untuk each dimension

### Pitfall 2: SMS as MFA untuk AAL2

**Problem:**
SMS OOB is **restricted** oleh NIST due to vulnerabilities (SIM swap, interception)

**Solution:**
- Prefer authenticator apps (TOTP)
- Or push notifications
- Or hardware tokens
- If SMS, add additional fraud checks

### Pitfall 3: Biometrics as Sole Authenticator

**Problem:**
"Fingerprint login adalah AAL2 karena biometric"

**Reality:**
- Biometric **alone** tidak sufficient untuk any AAL
- Must be bound to device atau software
- Example: Phone fingerprint unlock + device-bound key = multi-factor

**Solution:**
```
Correct: TouchID/FaceID unlocks device-bound key
  → Biometric (inherence) + Device key (possession)
  → AAL2 ✓

Incorrect: Server-side biometric comparison only
  → No second factor
  → Not AAL2 ✗
```

### Pitfall 4: Not Planning for Recovery

**Problem:**
User loses AAL2/AAL3 authenticator, no recovery path

**Solutions:**
- Backup authenticators
- Recovery codes (printed, stored safely)
- Support process dengan identity verification
- Don't make recovery easier than enrollment!

### Pitfall 5: Ignoring Session Management

**Problem:**
Strong authentication tapi weak session handling (cookies)

**Solution:**
- Session timeout appropriate untuk risk
- Re-auth untuk sensitive operations
- Secure session tokens (httpOnly, Secure flags)
- Logout functionality

---

## Kesimpulan dan Next Steps

### Kesimpulan Utama

1. **Risk-Based Approach**
   - NIST 800-63-3 adalah risk-driven framework
   - Select IAL, AAL, FAL based on impact
   - Higher level ≠ always better (balance dengan usability)

2. **Modular Framework**
   - IAL, AAL, FAL dapat dipilih independently
   - Flexibility untuk meet specific requirements
   - Cost-effective implementations

3. **Privacy-Focused**
   - Minimize PII collection
   - Pseudonymous options encouraged
   - User control over attribute sharing

4. **Technology Agnostic**
   - Framework tidak prescribe specific tech
   - Outcomes-based requirements
   - Allows untuk innovation

### Key Takeaways

| Aspect | Takeaway |
|--------|----------|
| **IAL** | Identity proofing strength - know WHO |
| **AAL** | Authentication strength - prove YOU ARE WHO |
| **FAL** | Federation security - SHARE SAFELY |
| **Implementation** | Use this guide untuk practical implementation |
| **Selection** | Risk assessment drives xAL choices |

### Recommended Next Steps

#### For Organizations Starting Out

1. **Conduct Risk Assessment**
   - Identify systems dan transactions
   - Assess impact of compromise
   - Categorize by risk level

2. **Map Current State**
   - What IAL, AAL, FAL are you currently achieving?
   - Identify gaps

3. **Prioritize Improvements**
   - Focus on high-risk systems first
   - Quick wins: Implement MFA (AAL2)
   - Longer term: Identity proofing improvements

#### For Implementations

1. **Read Normative Documents**
   - SP 800-63-3 (overview)
   - SP 800-63A (identity proofing)
   - SP 800-63B (authentication)
   - SP 800-63C (federation)

2. **Review Examples**
   - This implementation guide
   - NIST digital identity resources
   - Industry case studies

3. **Test Thoroughly**
   - Pilot dengan small user group
   - Security testing
   - Usability testing

4. **Document**
   - Practice statements
   - Risk assessments
   - Implementation decisions

---

## Referensi dan Sumber Tambahan

### NIST Publications

- **NIST SP 800-63-3:** Digital Identity Guidelines
- **NIST SP 800-63A:** Enrollment and Identity Proofing
- **NIST SP 800-63B:** Authentication and Lifecycle Management
- **NIST SP 800-63C:** Federation and Assertions
- **NIST SP 800-63-3 Implementation Resources:** (dokumen ini)

### Related Standards

- **FIDO2/WebAuthn:** Phishing-resistant authentication
- **FIPS 140:** Cryptographic module validation
- **SAML 2.0:** Federation standard
- **OpenID Connect:** Modern federation protocol
- **OAuth 2.0:** Authorization framework

### Online Resources

- **Implementation Resources Website:** https://pages.nist.gov/800-63-3-Implementation-Resources/
- **NIST Identity Page:** https://www.nist.gov/identity-access-management
- **FIDO Alliance:** https://fidoalliance.org/

---

## Glosarium

| Istilah | Penjelasan |
|---------|-----------|
| **IAL** | Identity Assurance Level - confidence bahwa identity adalah real |
| **AAL** | Authenticator Assurance Level - confidence bahwa claimant controls authenticator |
| **FAL** | Federation Assurance Level - assurance bahwa assertion secure |
| **CSP** | Credential Service Provider - entity yang issues credentials |
| **IdP** | Identity Provider - asserts identities dalam federation |
| **RP** | Relying Party - consumes assertions dari IdP |
| **Assertion** | Statement tentang subscriber dari IdP ke RP |
| **Authenticator** | Something used untuk authenticate (password, token, biometric) |
| **Credential** | Binding antara authenticator dan subscriber |
| **Claimant** | Party yang claiming identity |
| **Verifier** | Entity yang verifies claimant's authenticator |
| **MFA** | Multi-Factor Authentication |
| **OTP** | One-Time Password |
| **OOB** | Out-of-Band |
| **TOTP** | Time-based One-Time Password |
| **FIDO2** | Fast Identity Online 2 (phishing-resistant auth standard) |
| **PIV** | Personal Identity Verification (federal smart card) |
| **HoK** | Holder-of-Key (assertion binding) |
| **KBV** | Knowledge-Based Verification |
| **SAML** | Security Assertion Markup Language |
| **OIDC** | OpenID Connect |

---

**Catatan Penting:**

> [!WARNING]
> This implementation guide is **informative** (non-normative). Untuk compliance purposes, always refer ke normative requirements dalam SP 800-63-3, 63A, 63B, dan 63C.

**Dokumen ini berdasarkan:** NIST SP 800-63-3 Implementation Resources (1 Juli 2020)

**Untuk informasi terbaru, selalu rujuk ke:** https://pages.nist.gov/800-63-3-Implementation-Resources/
