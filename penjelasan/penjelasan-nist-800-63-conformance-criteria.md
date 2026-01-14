# Penjelasan NIST SP 800-63 Conformance Criteria: Panduan Testing dan Compliance

## Informasi Dokumen

**Judul:** NIST SP 800-63A/B/C Conformance Criteria

**Tanggal Publikasi:**
- 800-63A Conformance Criteria: Juni 2020
- 800-63B Conformance Criteria: Juni 2020
- 800-63C Conformance Criteria: April 2021

**Jumlah Halaman:**
- 800-63A: ~47 halaman
- 800-63B: 106 halaman
- 800-63C: 68 halaman

**Tipe Dokumen:** Non-normative testing guidance (panduan pengujian pelengkap)

**Kata Kunci:** Conformance Testing, Compliance Assessment, Identity Proofing Testing, Authentication Testing, Federation Testing, Audit Criteria

---

## Ringkasan Eksekutif

> [!IMPORTANT]
> **Conformance Criteria** adalah panduan **testing dan compliance assessment** untuk memverifikasi bahwa implementasi digital identity memenuhi persyaratan normatif NIST SP 800-63-3. Berbeda dengan Implementation Resources yang menjelaskan "how-to," Conformance Criteria menjelaskan "how-to-test."

**Hubungan Antar Dokumen:**

```
SP 800-63A/B/C (Normative)
  ↓ "WHAT requirements?"
  
Implementation Resources (Informative)
  ↓ "HOW to implement?"
  
Conformance Criteria (Testing)
  ↓ "HOW to verify compliance?"
```

**Target Audiens:**
- ✅ **Auditors** dan third-party assessors
- ✅ **Quality Assurance (QA)** teams
- ✅ **Procurement** officers (vendor validation)
- ✅ **Developers** (self-assessment)
- ✅ **Compliance** officers

---

## Mengapa Conformance Criteria Penting?

### Manfaat untuk Organisasi

1. **Objective Compliance Verification**
   - Kriteria yang clear dan measurable
   - Tidak ada ambiguitas dalam assessment
   - Repeatable testing methodology

2. **Vendor Validation**
   - Evaluate vendor claims dengan criteria terukur
   - Procurement requirements yang jelas
   - RFP/RFQ specifications

3. **Self-Assessment**
   - Develop internal audit checklists
   - Continuous compliance monitoring
   - Pre-audit preparation

4. **Risk Mitigation**
   - Identify gaps sebelum production
   - Reduce regulatory exposure
   - Demonstrate due diligence

### Assessment Methodology

**Three-Pronged Approach:**

| Method | Deskripsi | Contoh Aktivitas |
|--------|-----------|------------------|
| **EXAMINE** | Review dokumentasi dan konfigurasi | Policy documents, system design, configuration files, logs |
| **INTERVIEW** | Wawancara personel kunci | Privacy Officer, System Admin, Operators, Developers |
| **TEST** | Functional dan security testing | Penetration tests, negative testing, protocol verification |

---

## Part A: 800-63A Conformance Criteria (Identity Proofing)

### Overview

**Fokus:** Testing identity proofing dan enrollment processes

**Struktur Kriteria:**
- **20 General Requirements (GEN):** Applicable untuk all CSPs
- **15 IAL2-Specific Requirements**
- **9 IAL3-Specific Requirements**
- **8 Supervised Remote Proofing (SRP) Requirements**
- **3 Trusted Referee (TRR) Requirements**

### Format Setiap Kriteria

**Standard Format:**

```markdown
### GEN-X: [Requirement Title]

**Requirement (Normative):**
[Copied dari SP 800-63A - SHALL/SHALL NOT statement]

**Supplemental Guidance:**
[Context dan penjelasan tambahan untuk auditor]

**Assessment Objects:**
[List item yang harus diperiksa:]
  - Policy documents
  - System documentation
  - Process workflows
  - Configuration files
  - Audit logs

**Potential Assessment Methods:**
  - EXAMINE: [Dokumentasi apa yang direview]
  - INTERVIEW: [Siapa yang diwawancara, pertanyaan apa]
  - TEST: [Functional test apa yang dilakukan]
```

### General Requirements (GEN) - Key Criteria

#### GEN-1: Privacy Notice

**Requirement:**
CSP SHALL provide explicit notice ke applicant tentang pengumpulan, penggunaan, dan disclosure dari PII.

**Assessment Objects:**
- Privacy notice document
- Website/application enrollment page
- User consent forms

**Assessment Methods:**
- **EXAMINE:** Review privacy notice untuk completeness
- **INTERVIEW:** Privacy officer tentang notice distribution
- **TEST:** Navigate enrollment flow untuk verify notice displayed

**Apa yang Diverifikasi:**
- ✅ Notice provided **sebelum** atau **selama** enrollment
- ✅ Mencakup **apa** dikumpulkan, **mengapa**, **siapa** dapat akses
- ✅ User acknowledgment atau consent mechanism
- ❌ Notice tidak tersembunyi dalam TOS yang panjang

#### GEN-2: Collection Limitation

**Requirement:**
CSP SHALL collect minimum attributes necessary untuk identity proofing.

**Assessment:**
- **EXAMINE:** List attributes collected during enrollment
- Compare dengan evidence strength requirements di Appendix B
- Identifikasi attributes yang berlebihan (over-collection)

**Common Failures:**
- ❌ Collecting SSN jika tidak strictly necessary
- ❌ Mandatory fields untuk optional attributes
- ❌ Collecting attributes untuk marketing (bukan proofing)

#### GEN-3 to GEN-20

Other General Requirements cover:
- **GEN-3:** Attribute validation mechanisms
- **GEN-4:** Biometric collection (jika applicable)
- **GEN-5 - GEN-10:** Resolution, Validation, Verification phases
- **GEN-11 - GEN-15:** Evidence strength requirements
- **GEN-16 - GEN-20:** Security, fraud prevention, breach response

### IAL2 Testing Criteria

#### IAL2-1: Evidence Requirements

**Requirement:**
IAL2 requires validation dan verification dari identity evidence.

**Testing Approach:**

**Test Case 1: Evidence Strength Validation**
```
Test: Submit driver's license untuk identity proofing
Verify:
  ✅ System validates against DMV database (STRONG evidence)
  ✅ Security features checked (barcode, hologram)
  ✅ Expiration date verified
  
Negative Test: Submit expired license
Expected Result:
  ❌ System SHALL reject atau flag untuk manual review
```

**Test Case 2: Multiple Evidence Sources**
```
Test: Attempt enrollment dengan satu FAIR evidence only
Expected Result:
  ❌ SHALL NOT achieve IAL2 (requires STRONG atau SUPERIOR)
```

#### IAL2-2: Remote Identity Proofing

**Requirement:**
Remote proofing acceptable untuk IAL2 dengan proper verification.

**Testing:**
- **Biometric Matching Test:**
  - Submit selfie yang tidak match dengan ID photo
  - Expected: Rejection atau manual review flag

- **Liveness Detection:**
  - Attempt spoof dengan printed photo
  - Expected: Liveness check detects dan rejects

- **Knowledge-Based Verification (KBV):**
  - Answer KBV questions incorrectly
  - Expected: Proofing fails

#### Appendix B: Evidence Strength Tables

**Critical Testing Tool:**

Dokumen includes detailed tables untuk:
- **Identity Evidence Strength:** SUPERIOR, STRONG, FAIR, WEAK
- **Mapping:** Document types → Strength ratings

**Example:**
```
SUPERIOR:
  - Passport dengan crypto verification
  - PIV card dengan PKI

STRONG:
  - State-issued driver's license
  - Utility bill dari authoritative source

FAIR:
  - Student ID card
  - Bank statement (dari self-reported institution)
```

**Testing Approach:**
- Audit actual evidence types accepted
- Map ke Appendix B ratings
- Verify strength combinations meet IAL requirements

---

## Part B: 800-63B Conformance Criteria (Authentication)

### Overview

**Fokus:** Authenticator testing dan session management

**Struktur Kriteria (106 halaman):**

**Category Codes:**
- **MS:** Memorized Secret (password)
- **OOB:** Out-of-Band
- **OTP:** One-Time Password
- **CRYP:** Cryptographic Authenticators
- **BIO:** Biometric
- **SESS:** Session Management
- **REAUTH:** Reauthentication
- **BIND:** Authenticator Binding

**AAL Levels:**
- AAL1: 基本 criteria
- AAL2: Additional multi-factor requirements
- AAL3: Hardware-based, phishing-resistant

### Memorized Secret (MS) Testing

#### MS-1: Password Length

**Requirement:**
- User-chosen: ≥ 8 characters
- System-generated: ≥ 6 characters

**Test Cases:**

**Positive Test:**
```
Test: Create password dengan 8 chars
Expected: ✅ Accepted
```

**Negative Tests:**
```
Test 1: Password dengan 7 chars
Expected: ❌ Rejected dengan error message

Test 2: System-generated password dengan 5 chars
Expected: ❌ System SHALL NOT generate ini
```

**Assessment Method:**
- **EXAMINE:** Password policy configuration
- **TEST:** Attempt various length passwords
- **INTERVIEW:** Developers tentang validation logic

#### MS-2: No Complexity Requirements

**Requirement:**
SHALL NOT impose composition rules (e.g., kecuali uppercase, numbers, special chars)

**Why:** Research shows complexity rules → weaker passwords (e.g., "Password1!")

**Test:**
```
Test: Create password "longpassphrase" (all lowercase)
Expected: ✅ Should be accepted
  
Negative Test: System rejects karena "needs uppercase"
Finding: ❌ VIOLATION of NIST requirement
```

#### MS-3: Password Blacklist

**Requirement:**
Check passwords against commonly-used, expected, або compromised passwords.

**Test:**
```
Test: Attempt passwords:
  - "password"
  - "123456"
  - "qwerty"
  - Password from breach database
  
Expected: ❌ All SHALL be rejected
```

**Assessment:**
- **EXAMINE:** Blacklist source (e.g., HIBP, common password lists)
- **TEST:** Submit known weak passwords
- **INTERVIEW:** How blacklist is maintained dan updated

#### MS-4: Allow Paste

**Requirement:**
SHALL allow paste functionality (untuk password managers)

**Test:**
```
Test: Copy strong password dan paste into field
Expected: ✅ Paste should work
  
Negative Finding: Field blocks paste (e.g., onpaste="return false")
Result: ❌ VIOLATION
```

#### MS-5: Hashing dan Salt

**Requirement:**
- Approved hash function (e.g., PBKDF2, bcrypt, scrypt, Argon2)
- Salt minimal 32 bits

**Assessment:**
- **EXAMINE:** Source code atau documentation
- **INTERVIEW:** Developers tentang implementation
- **TEST:** (Whitebox) Verify database storage format tidak plain text

**Verification:**
```
Database Entry Should Look Like:
$2a$12$R9h/cIPz0gi.URNNX3kh2OPST9/PgBkqquzi.Ss7KIUgO2t0jWMUW
  ↑    ↑   ↑
  alg  cost  salt + hash
  
NOT:
plain_password_123
```

### Out-of-Band (OOB) Testing

#### OOB-1: SMS Restrictions

**Requirement:**
SMS OOB is **RESTRICTED** untuk AAL2+ (due to SIM swap vulnerabilities)

**Test:**
```
Scenario: AAL2 implementation using SMS untuk 2nd factor
  
Assessment Questions:
  - Apakah ada risk assessment documenting SMS risks?
  - Apakah ada compensating controls? (e.g., fraud detection)
  - Apakah SMS only fallback, bukan primary MFA?
  
Finding: May be acceptable dengan documented risk acceptance
```

#### OOB-2: Single-Use Verification Code

**Requirement:**
OOB codes SHALL be single-use

**Test:**
```
Test Case:
1. Request OOB code
2. Receive code "12345"
3. Use code → Access granted ✅
4. Attempt code "12345" again → Access denied ❌

Expected: Second attempt SHALL fail
```

**Common Failure:**
Code can be reused within validity window

#### OOB-3: Code Expiration

**Requirement:**
OOB codes have limited validity (typically 10 minutes)

**Test:**
```
Test:
1. Request code
2. Wait 11 minutes
3. Attempt to use code

Expected: ❌ Code expired dan rejected
```

### One-Time Password (OTP) Testing

#### OTP-1: TOTP Implementation

**Requirement:**
Time-based OTP SHALL use approved algorithm (HMAC-SHA-1/256/512)

**Assessment:**
- **EXAMINE:** TOTP library atau implementation
- **TEST:** Generate codes dan verify time-sync
- **INTERVIEW:** Clock sync mechanisms

**Test:**
```
Test: Verify TOTP codes change every 30 seconds
  
Steps:
1. Generate code at T=0
2. Generate code at T=30
3. Verify codes are different
4. Attempt T=0 code at T=35
Expected: First code rejected (expired)
```

#### OTP-2: Replay Protection

**Requirement:**
Verifier SHALL check OTP code hasn't been used previously

**Test:**
```
Test Case: OTP Replay Attack
1. User authenticates dengan OTP "987654"
2. Attacker captures code
3. Attacker attempts authentication dengan sama code "987654"

Expected: ❌ Second attempt denied (code already used)
```

### Cryptographic Authenticator Testing

#### CRYP-1: FIPS 140 Validation

**Requirement:**
Government AAL2+ requires FIPS 140 Level 1 (minimum)

**Assessment:**
- **EXAMINE:** FIPS 140 certificate for hardware/module
- **VERIFY:** Certificate aktif (not revoked)
- **CHECK:** Certificate covers algorithms used

**Resources:**
- NIST CMVP (Cryptographic Module Validation Program) database
- https://csrc.nist.gov/Projects/cryptographic-module-validation-program

#### CRYP-2: Private Key Protection

**Requirement:**
Private keys SHALL NOT leave cryptographic device (AAL3)

**Test:**
```
Test: Attempt to export private key dari hardware token
Expected: ❌ Operation not permitted
  
Whitebox Test: Review code untuk key storage
Finding: Keys stored di hardware-backed keystore (✅)
       or Keys exportable (❌ VIOLATION untuk AAL3)
```

### Session Management (SESS) Testing

#### SESS-1: Session Secret Generation

**Requirement:**
Session identifiers SHALL be generated dengan approved random number generator

**Assessment:**
- **EXAMINE:** Session ID generation code
- **TEST:** Collect sample session IDs dan analyze untuk randomness
- **INTERVIEW:** Developers tentang RNG used

**Negative Finding:**
```
❌ Sequential session IDs (e.g., session_100, session_101)
❌ Predictable patterns
❌ Insufficient entropy
```

#### SESS-2: Session Timeout

**Requirement:**
Idle timeout requirements vary by AAL:
- AAL1: 30 minutes maximum idle
- AAL2: 15 minutes  recommended
- AAL3: 15 minutes maximum idle

**Test:**
```
Test for AAL2:
1. User authenticates
2. Remain idle untuk 20 minutes
3. Attempt transaction

Expected: ❌ Session timeout → re-authentication required
```

#### SESS-3: CSRF Protection

**Requirement:**
Protection against Cross-Site Request Forgery

**Test:**
```
Penetration Test:
1. User authenticated ke application
2. Attacker crafts malicious request with user's session ID
3. User clicks attacker link (CSRF attempt)

Expected: ✅ Request rejected (CSRF token validation)
```

**Implementation Check:**
- Anti-CSRF tokens present?
- SameSite cookie attribute set?
- Additional origin validation?

#### SESS-4: TLS/SSL Enforcement

**Requirement:**
Authenticated sessions SHALL use TLS

**Test:**
```
Test: Attempt downgrade attack
1. User authenticates via HTTPS
2. Manually modify URL to HTTP
3. Attempt transaction

Expected: ❌ Connection rejected atau auto-redirect ke HTTPS
```

**Verification:**
- HSTS (HTTP Strict Transport Security) header present?
- TLS version ≥ 1.2?
- Strong cipher suites only?

### Reauthentication (REAUTH) Testing

#### REAUTH-1: Periodic Reauthentication

**Requirement:**
AAL3 requires reauthentication every 12 hours (maximum)

**Test:**
```
Test for AAL3:
1. User authenticates di 8:00 AM
2. User remains active
3. At 8:01 PM (12h 1min), attempt transaction

Expected: Reauthentication required
```

#### REAUTH-2: Privileged Operations

**Requirement:**
Step-up authentication untuk sensitive operations

**Test:**
```
Scenario: Banking application
1. User logged in dengan password only (AAL1)
2. Attempt high-value transfer ($10,000)

Expected: System prompts untuk second factor (step-up ke AAL2)
```

---

## Part C: 800-63C Conformance Criteria (Federation)

### Overview

**Fokus:** Federation protocol dan assertion testing

**Struktur (68 halaman):**

**Categories:**
- **General Federation Requirements**
- **Front-Channel Criteria** (browser-based flows)
- **Back-Channel Criteria** (server-to-server)
- **Assertion Criteria**
- **Privacy Criteria**
- **FAL-Specific Requirements** (FAL1, FAL2, FAL3)

### General Federation Requirements

#### FED-1: IdP and RP Trust Relationship

**Requirement:**
IdP dan RP harus establish trust sebelum federation

**Assessment:**
- **EXAMINE:** Trust agreements atau contracts
- **EXAMINE:** Configuration (metadata exchanges, certificates)
- **INTERVIEW:** How trust established dan maintained

**Verification:**
- Federation metadata properly configured?
- Certificates validated dan not expired?
- Trust revocation procedures documented?

#### FED-2: Assertion Audience Restriction

**Requirement:**
Assertions SHALL be audience-restricted ke specific RP

**Test:**
```
Test: Assertion Injection Attack
1. IdP issues assertion untuk RP-A
2. Attacker captures assertion
3. Attacker attempts to use assertion di RP-B

Expected: ❌ RP-B rejects (audience mismatch)
```

**Verification dalam Assertion:**
```xml
<saml:Audience>https://rp-a.example.com</saml:Audience>

RP-B checks:
  if (assertion.audience != "https://rp-b.example.com") {
    reject(); // ✅ Correctly rejects
  }
```

### Front-Channel Testing

#### FRONT-1: Browser Redirection Security

**Requirement:**
Front-channel SHALL protect against open redirect vulnerabilities

**Test:**
```
Attack Scenario:
1. Attacker crafts URL:
   https://idp.example.com/login?redirect=https://evil.com
2. User clicks link
3. After authentication, apa user redirected ke evil.com?

Expected: ❌ IdP validates redirect target dalam whitelist
```

#### FRONT-2: State Parameter (CSRF for OAuth/OIDC)

**Requirement:**
OAuth 2.0 / OIDC SHALL use "state" parameter untuk CSRF protection

**Test:**
```
Test:
1. RP initiates flow dengan state="abc123xyz"
2. Attacker attempts to inject different state
3. IdP returns dengan original state
4. RP validates state matches

Expected: ✅ RP rejects jika state mismatch
```

### Back-Channel Testing

#### BACK-1: TLS Mutual Authentication

**Requirement:**
Back-channel communication MAY use mutual TLS

**Assessment:**
- **EXAMINE:** TLS configuration untuk back-channel
- **TEST:** Attempt connection tanpa client certificate (jika mTLS required)
- **VERIFY:** Certificate validation logic

#### BACK-2: Token/Reference Binding

**Requirement:**
Authorization codes atau assertion references SHALL be single-use

**Test (OIDC Example):**
```
Test: Authorization Code Replay
1. User completes OIDC flow
2. RP receives authorization code "code_xyz"
3. RP exchanges code untuk tokens (✅ Success)
4. Attacker captures "code_xyz"
5. Attacker attempts exchange

Expected: ❌ IdP rejects (code already used)
```

#### BACK-4: Reference Injection (Critical Test)

**Requirement:**
Assertion references SHALL NOT be usable by unintended RPs

**Test:**
```
SAML Artifact Example:
1. IdP issues artifact reference untuk RP-A
2. Attacker intercepts reference
3. Attacker (di RP-B) attempts to dereference artifact

Expected: ❌ IdP returns error (artifact bound ke RP-A)
```

### Assertion Validation Testing

#### ASSERT-1: Signature Verification

**Requirement:**
Assertions SHALL be cryptographically signed

**Tests:**

**Test 1: Missing Signature**
```
Test: Remove signature dari assertion dan submit
Expected: ❌ RP rejects immediately
```

**Test 2: Invalid Signature**
```
Test: Modify assertion content (e.g., change subject)
Expected: ❌ Signature validation fails → rejection
```

**Test 3: Wrong Signing Key**
```
Test: Sign assertion dengan key tidak trusted oleh RP
Expected: ❌ RP rejects (key not in trusted keyset)
```

#### ASSERT-2: Temporal Validation

**Requirement:**
RPs SHALL check NotBefore dan NotOnOrAfter timestamps

**Tests:**

**Test 1: Future-Dated Assertion**
```
Assertion:
  NotBefore: 2026-01-15 00:00:00 UTC
  Current Time: 2026-01-14 23:00:00 UTC

Expected: ❌ RP rejects (assertion not yet valid)
```

**Test 2: Expired Assertion**
```
Assertion:
  NotOnOrAfter: 2026-01-14 10:00:00 UTC
  Current Time: 2026-01-14 10:05:00 UTC

Expected: ❌ RP rejects (assertion expired)
```

**Test 3: Clock Skew Tolerance**
```
Test: Assertion dengan timestamp slight drift (within tolerance)
Expected: ✅ Accepted (e.g., 5 min tolerance)
```

#### ASSERT-3: Issuer Validation

**Requirement:**
RP SHALL verify assertion issuer is expected IdP

**Test:**
```
Attack: Assertion Spoofing
1. Attacker creates assertion claiming issuer="https://idp.example.com"
2. Attacker signs dengan own key
3. Submits ke RP

Expected: ❌ RP checks issuer AND validates signature
       → Signature invalid untuk claimed issuer → Rejected
```

### Privacy Testing

#### ID-6: Privacy Risk Assessment

**Requirement:**
RP SHALL conduct privacy risk assessment sebelum requesting common identifiers

**Assessment:**
- **EXAMINE:** Privacy impact assessment documents
- **INTERVIEW:** Privacy Officer tentang assessment process
- **VERIFY:** Justification untuk requesting specific attributes

**Red Flag:**
```
❌ RP requests SSN untuk simple forum login (disproportionate)
❌ No documented privacy risk assessment
```

#### ID-7: Pairwise Pseudonymous Identifiers

**Requirement:**
IdPs SHOULD use pairwise identifiers untuk prevent correlation across RPs

**Test:**
```
Test: Identifier Correlation
1. User authenticates to RP-A → receives identifier "uuid-123"
2. Same user authenticates to RP-B → receives identifier "uuid-456"
3. Verify RP-A dan RP-B cannot correlate

Expected: ✅ Different identifiers prevent tracking
```

**Verification:**
- IdP configuration supports pairwise identifiers?
- Documented cases when global identifier necessary?

### FAL3 Specific Testing

#### FAL3-1: Holder-of-Key Assertion

**Requirement:**
FAL3 requires holder-of-key mechanism

**Test:**
```
Test: Assertion with Key Reference
1. IdP issues assertion containing reference ke user's public key
2. RP challenges user untuk prove possession of private key
3. User must sign challenge dengan private key
4. RP validates signature

Negative Test: Attacker replays assertion without key
Expected: ❌ RP challenges untuk key proof → Attacker cannot respond
```

#### FAL3-2: Assertion Encryption

**Requirement:**
FAL3 assertions SHALL be encrypted

**Test:**
```
Test: Assertion Confidentiality
1. Capture network traffic during federation
2. Examine assertion content
Expected: ✅ Assertion encrypted (ciphertext only visible)
       ❌ Plaintext readable → VIOLATION
```

**Verification:**
- Encryption algorithm approved?
- Encryption keys properly managed?
- Key agreement protocol secure?

#### FAL3-3: Key Verification

**Requirement:**
RP SHALL verify key dalam holder-of-key assertion

**Test:**
```
Negative Test: Key Substitution Attack
1. Attacker obtains legitimate assertion
2. Attacker replaces key reference dengan own public key
3. Attacker submits modified assertion
4. RP challenges Attacker → Attacker responds dengan own private key

Expected: ❌ RP detects key tampering (signature validation)
       or RP binds key ke original authentication event
```

---

## Practical Testing Scenarios

### Scenario 1: Auditing a Banking Application (IAL2/AAL2)

**Scope:** Verify compliance with NIST 800-63 untuk online banking

**Step 1: Identity Proofing Audit (IAL2)**

**Checklist:**
```
□ Examine privacy notice presented during enrollment
□ Verify evidence types accepted (driver's license, passport)
□ Test evidence validation (barcode scan, DMV lookup)
□ Test biometric matching (selfie vs ID photo)
□ Verify Knowledge-Based Verification (KBV) implementation
□ Interview operators tentang manual review process
□ Check fraud detection mechanisms
```

**Test Case:**
```
Test: Attempt enrollment dengan fake ID
Procedure:
  1. Submit obviously fake driver's license
  2. Observe system response
  
Expected: Detection via:
  - Automated validation failure (barcode, security features)
  - Failing DMV lookup
  - Manual review flag
```

**Step 2: Authentication Audit (AAL2)**

**Checklist:**
```
□ Verify MFA implementation (password + OTP / hardware token)
□ Test password policy (length, blacklist, no complexity rules)
□ Verify FIPS 140 certificate untuk hardware tokens
□ Test session timeout (15 min idle untuk AAL2)
□ Verify CSRF protection
□ Test TLS enforcement
□ Verify reauthentication untuk high-value transactions
```

**Test Case:**
```
Test: MFA Bypass Attempt
Procedure:
  1. Login dengan valid password
  2. Interrupt MFA step (close browser, skip)
  3. Attempt direct access ke application

Expected: ❌ Access denied until MFA completed
```

**Step 3: Documentation Review**

**Required Documents:**
```
□ System Security Plan (SSP)
□ Privacy Impact Assessment (PIA)
□ Incident Response Plan
□ Practice Statement (identity proofing procedures)
□ Password policy document
□ Session management specification
□ Penetration test results
□ FIPS 140 certificates
```

**Step 4: Interview Personnel**

**Questions untuk different roles:**

**Privacy Officer:**
- How is user PII protected?
- Data retention policies?
- Breach notification procedures?

**System Administrator:**
- Session management configuration?
- Logging dan monitoring?
- Incident response procedures?

**Developers:**
- Password hashing implementation?
- CSRF protection mechanisms?
- Third-party library versions?

### Scenario 2: Federation Testing (FAL2)

**Scope:** SAML-based SSO between employer IdP dan cloud application RP

**Front-Channel Tests:**

**Test 1: Assertion Capture dan Replay**
```
Procedure:
1. Complete SAML SSO flow
2. Browser interceptor captures SAML assertion
3. Wait 5 minutes
4. Replay assertion dalam new browser

Expected:
  ❌ RP rejects due to:
     - Assertion already consumed (single-use)
     - atau Timestamp expired
```

**Test 2: Assertion Modification**
```
Procedure:
1. Capture SAML assertion
2. Modify user attributes (e.g., role: user → admin)
3. Replay modified assertion

Expected:
  ❌ Signature validation fails → Rejected
```

**Back-Channel Tests:**

**Test 3: Reference Hijacking**
```
Procedure (SAML Artifact binding):
1. User completes SSO to RP-A
2. Capture artifact reference
3. Setup malicious RP-B
4. Attempt dereference artifact from RP-B

Expected:
  ❌ IdP checks artifact bound ke RP-A → Rejects RP-B
```

**Privacy Tests:**

**Test 4: Attribute Minimization**
```
Audit:
1. Examine attributes released dalam assertion
2. Compare dengan RP's actual needs
  
Finding Examples:
  ✅ Email address untuk login → Justified
  ❌ SSN atau Date of Birth → Not needed untuk simple app access
```

**Test 5: Pairwise Identifiers**
```
Procedure:
1. User logs in ke RP-A → Note identifier
2. Same user logs in ke RP-B → Note identifier
3. Compare identifiers

Expected:
  ✅ Different identifiers (pairwise)
  ❌ Same identifier globally → Privacy risk
```

---

## Common Pitfalls dan How Auditors Catch Them

### Pitfall 1: Insufficient Evidence Validation (IAL)

**Implementation Error:**
```python
# BAD: Self-asserted evidence tidak validated
def enroll_user(name, dob, ssn):
    # Just save whatever user enters
    create_account(name=name, dob=dob, ssn=ssn)
    return success
```

**How Auditor Catches:**
- **EXAMINE:** Code review shows no validation
- **INTERVIEW:** "How do you verify SSN adalah valid?"
- **TEST:** Submit fake SSN "123-45-6789" → Accepted ❌

**Correct Implementation:**
```python
# GOOD: Validates against authoritative source
def enroll_user(name, dob, ssn):
    # Validate SSN dengan Social Security Administration
    if not validate_ssn(ssn):
        return error("Invalid SSN")
    
    # Cross-check name + DOB + SSN
    if not verify_identity(name, dob, ssn):
        return error("Identity verification failed")
    
    create_account(name, dob, ssn)
    return success
```

### Pitfall 2: Weak Password Hashing

**Implementation Error:**
```javascript
// BAD: MD5 without salt
const hashedPassword = md5(password);
```

**How Auditor Catches:**
- **EXAMINE:** Code review atau configuration
- **TEST:** (Whitebox) Database inspection
- **INTERVIEW:** "What hash algorithm do you use?"

**Finding:**
```
Database Passwords:
5f4dcc3b5aa765d61d8327deb882cf99  ← MD5 of "password"
5ebe2294ecd0e0f08eab7690d2a6ee69  ← MD5 of "secret"

Auditor: ❌ VIOLATION
  - MD5 not approved
  - No salt visible
  - Rainbow table attack possible
```

**Correct Implementation:**
```python
# GOOD: bcrypt dengan salt
import bcrypt

salt = bcrypt.gensalt()  # 32+ bit salt
hashed = bcrypt.hashpw(password.encode(), salt)

# Database:
# $2b$12$KIXxLVhPzT9F.lCK2C3jvO7eJ.4VkFz...
#  ↑    ↑   ↑
#  alg cost salt+hash
```

### Pitfall 3: Reusable OOB Codes

**Implementation Error:**
```python
# BAD: Code valid indefinitely dan reusable
def verify_oob_code(user_id, code):
    stored_code = get_oob_code(user_id)
    if code == stored_code:
        return success  # No expiry, no single-use enforcement
    return failure
```

**How Auditor Catches:**
- **TEST:** Use OOB code twice
  - First use: Success ✅
  - Second use: Success ❌ (Should fail!)

**Correct Implementation:**
```python
# GOOD: Single-use dengan expiration
def verify_oob_code(user_id, code):
    record = get_oob_record(user_id)
    
    # Check expiration
    if datetime.now() > record.expires_at:
        return failure("Code expired")
    
    # Check code match
    if code != record.code:
        return failure("Invalid code")
    
    # Check not already used
    if record.used:
        return failure("Code already used")
    
    # Mark as used (single-use)
    mark_code_used(record.id)
    return success
```

### Pitfall 4: Missing CSRF Protection

**Implementation Error:**
```html
<!-- BAD: No CSRF token -->
<form action="/transfer" method="POST">
  <input name="to_account" />
  <input name="amount" />
  <button>Transfer</button>
</form>
```

**How Auditor Catches:**
- **EXAMINE:** View page source - no CSRF token
- **TEST:** Craft malicious page:
  ```html
  <!-- Attacker's page -->
  <form action="https://bank.example.com/transfer" method="POST">
    <input name="to_account" value="attacker_account" />
    <input name="amount" value="10000" />
  </form>
  <script>document.forms[0].submit();</script>
  ```
  - If user visits while logged in → Transfer executes ❌

**Correct Implementation:**
```html
<!-- GOOD: CSRF token included -->
<form action="/transfer" method="POST">
  <input type="hidden" name="csrf_token" value="abc123xyz...">
  <input name="to_account" />
  <input name="amount" />
  <button>Transfer</button>
</form>
```

```python
# Server-side validation
def handle_transfer(request):
    if request.csrf_token != session.csrf_token:
        return error("CSRF validation failed")
    # Process transfer...
```

### Pitfall 5: Assertion Replay (Federation)

**Implementation Error:**
```python
# BAD: No replay protection
def consume_assertion(assertion):
    if verify_signature(assertion):
        user_id = assertion.subject
        create_session(user_id)
        return success
    return failure
```

**How Auditor Catches:**
- **TEST:** Capture assertion dan replay
  - Capture signed SAML assertion
  - Wait 2 minutes
  - POST same assertion again
  - Result: New session created ❌ (Should be rejected!)

**Correct Implementation:**
```python
# GOOD: Replay protection
def consume_assertion(assertion):
    # Verify signature
    if not verify_signature(assertion):
        return failure("Invalid signature")
    
    # Check not already consumed
    assertion_id = assertion.get_id()
    if is_consumed(assertion_id):
        return failure("Assertion already used")
    
    # Check temporal validity
    if not check_timestamps(assertion):
        return failure("Assertion expired atau not yet valid")
    
    # Mark as consumed
    mark_consumed(assertion_id)
    
    # Create session
    user_id = assertion.subject
    create_session(user_id)
    return success
```

---

## Audit Planning dan Execution

### Pre-Audit Preparation

**For Organizations Being Audited:**

**1. Self-Assessment (3-6 months before):**
```
Week 1-2: Review Conformance Criteria documents
Week 3-4: Map current implementation ke criteria
Week 5-8: Identify gaps
Week 9-12: Remediate critical gaps
```

**2. Documentation Preparation:**
- Ensure all documents up-to-date
- Practice statement finalized
- Privacy notices reviewed
- Security policies documented

**3. Technical Preparation:**
- Fix known vulnerabilities
- Update FIPS certificates
- Verify logging mechanisms
- Test backup authentication methods

**4. Personnel Preparation:**
- Identify key personnel untuk interviews
- Brief team on likely questions
- Ensure developer availability untuk code reviews

### Audit Execution

**Typical Audit Timeline:**

**Day 1: Kickoff dan Documentation Review**
- Opening meeting
- Scope confirmation
- Request dan review documents
- Initial interviews (Privacy Officer, CISO)

**Day 2-3: Technical Testing**
- Identity proofing tests
- Authentication tests
- Federation tests (jika applicable)
- Code reviews
- Configuration reviews

**Day 4: Interviews dan Validation**
- Developer interviews
- System administrator interviews
- Observation of processes
- Validation of findings

**Day 5: Closeout**
- Findings review
- Closeout meeting
- Report outline discussion

### Post-Audit

**Audit Report Structure:**

```markdown
# Conformance Assessment Report

## Executive Summary
- Overall compliance status
- Key findings
- Risk rating

## Detailed Findings

### IAL Compliance
- [List findings dengan severity]
  
### AAL Compliance
- [List findings dengan severity]
  
### FAL Compliance (if applicable)
- [List findings dengan severity]

## Recommendations
- [Prioritized remediation plan]

## Conclusion
- [Assessment opinion]
```

**Finding Severity Levels:**

| Severity | Description | Example |
|----------|-------------|---------|
| **CRITICAL** | Non-compliance dengan SHALL requirement | No password hashing, plaintext storage |
| **HIGH** | Significant gap dalam security controls | Weak hashing algorithm, no MFA |
| **MODERATE** | Incomplete implementation | Partial CSRF protection, weak entropy |
| **LOW** | Best practice recommendations | UI/UX improvements, documentation gaps |
| **INFORMATIONAL** | Observations, no compliance impact | Code style, future considerations |

**Plan of Action and Milestones (POA&M):**

```
Finding ID: AUTH-003
Severity: HIGH
Description: MFA not implemented untuk AAL2 systems
  
Remediation:
  - Milestone 1: Evaluate MFA solutions (30 days)
  - Milestone 2: Procure dan deploy MFA (60 days)
  - Milestone 3: User training dan rollout (90 days)
  - Milestone 4: Full implementation (120 days)
  
Owner: IT Security Manager
Due Date: [120 days from report]
```

---

## Tools dan Resources

### Testing Tools

**Identity Proofing:**
- **Document Verification Tools:** Acuant, Jumio, Onfido
- **Biometric Matching:** FaceFirst, Aware
- **KBV Services:** LexisNexis, Experian

**Authentication Testing:**
- **Password Analysis:** zxcvbn, HIBP API
- **TOTP Testing:** Google Authenticator, Microsoft Authenticator
- **Security Scanners:** OWASP ZAP, Burp Suite

**Federation Testing:**
- **SAML Tools:** SAML-tracer browser plugin, SAMLTest.id
- **OIDC Tools:** jwt.io, oidcdebugger.com
- **Protocol Analyzers:** Wireshark, Fiddler

### Reference Documents

**NIST Publications:**
- SP 800-63-3 (Digital Identity Guidelines)
- SP 800-63A (Enrollment and Identity Proofing)
- SP 800-63B (Authentication and Lifecycle Management)
- SP 800-63C (Federation and Assertions)
- SP 800-63-3 Implementation Resources

**Related Standards:**
- ISO/IEC 29115 (Entity Authentication Assurance)
- FIDO Alliance Specifications
- OAuth 2.0 / OpenID Connect RFCs

---

## Kesimpulan dan Rekomendasi

### Key Takeaways

1. **Conformance Criteria = Testing Checklist**
   - Tidak ada ambiguitas dalam requirements
   - Objective, measurable criteria
   - Repeatable methodology

2. **Three-Method Approach**
   - EXAMINE + INTERVIEW + TEST
   - Combination provides comprehensive assessment
   - Each method validates different aspects

3. **Negative Testing Critical**
   - Don't just test happy path
   - Attempt to bypass security
   - Verify rejections happen correctly

4. **Documentation Matters**
   - Auditors need evidence
   - Well-documented systems easier to assess
   - Practice statements dan policies essential

### Best Practices untuk Compliance

**For Implementers:**
- ✅ Use conformance criteria sebagai development checklist
- ✅ Self-assess before external audit
- ✅ Document everything
- ✅ Test with security mindset (negative tests)

**For Auditors:**
- ✅ Plan assessments carefully
- ✅ Use multiple assessment methods
- ✅ Document findings with evidence
- ✅ Provide actionable recommendations

**For Procurement:**
- ✅ Reference specific conformance criteria dalam RFP/RFQ
- ✅ Require vendor attestation atau certification
- ✅ Validate vendor claims dengan testing
- ✅ Include compliance dalam SLAs

### Next Steps

**For Organizations Pursuing Compliance:**

1. **Gap Analysis** (Month 1)
   - Compare current state ke conformance criteria
   - Prioritize based on risk

2. **Remediation Planning** (Month 2)
   - Develop POA&M
   - Allocate resources
   - Set timelines

3. **Implementation** (Months 3-6)
   - Execute remediation
   - Document changes
   - Test continuously

4. **Assessment** (Month 7)
   - Self-assessment atau third-party audit
   - Address findings
   - Achieve compliance

5. **Continuous Monitoring** (Ongoing)
   - Regular testing
   - Update documentation
   - Monitor for changes in requirements

---

## Glosarium

| Istilah | Penjelasan |
|---------|-----------|
| **Conformance** | Compliance dengan normative requirements |
| **Assessment** | Evaluation process untuk verify conformance |
| **Auditor** | Independent party conducting assessment |
| **Assessor** | Third-party evaluator (similar ke auditor) |
| **Finding** | Non-compliance atau gap identified dalam assessment |
| **POA&M** | Plan of Action and Milestones untuk remediation |
| **Practice Statement** | Document describing CSP processes dan procedures |
| **Negative Testing** | Testing dengan invalid/malicious inputs |
| **Whitebox Testing** | Testing dengan access ke internals (code, config) |
| **Blackbox Testing** | Testing without internal knowledge |

---

**Catatan Penting:**

> [!TIP]
> Conformance Criteria bersifat **non-normative** tetapi sangat penting. Mereka menjelaskan **how to test** normative requirements, making compliance objective dan verifiable.

**Dokumen ini berdasarkan:**
- NIST SP 800-63A Conformance Criteria (Juni 2020)
- NIST SP 800-63B Conformance Criteria (Juni 2020)
- NIST SP 800-63C Conformance Criteria (April 2021)

**Untuk informasi terbaru, selalu rujuk ke:** https://pages.nist.gov/800-63-3-Implementation-Resources/
