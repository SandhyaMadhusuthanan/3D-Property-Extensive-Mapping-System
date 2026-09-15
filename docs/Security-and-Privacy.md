# Security and Privacy

## Current Prototype Status

The current prototype (`prototype/index.html`) is a **local, client-only demo**:
- Login is simulated — credentials are checked against hardcoded values in the JavaScript, not a real authentication server.
- All data shown (households, ownership, values) is **mock/sample data** for the fictional Salem city dataset. No real personal data, Aadhaar numbers, or government records are used or transmitted anywhere.
- There is no network call, no external API, and no data storage — nothing entered by a user is saved or sent anywhere.

This section describes the security and privacy model that would be **required for a real, production deployment** of this system.

## 1. Identity & Access Control
- Real deployments must use **Aadhaar e-KYC or an equivalent verified government ID** for login — never a simple username/password as in the current demo.
- **Role-based access control (RBAC):** Government Officials should only see what their jurisdiction/role permits; Citizens should only see their own linked records, never another person's ownership or household details.
- Session tokens should be short-lived, with mandatory re-authentication for sensitive actions (e.g., viewing another member's Aadhaar-linked share details, or initiating a share transfer).

## 2. Data Sensitivity Classification
| Data Type | Sensitivity | Handling Requirement |
|---|---|---|
| Base ULPIN, plot boundaries | Public/Low | Can be shown on public maps |
| Ownership names, share % | Medium | Visible only to Govt Officials and the owners themselves |
| Aadhaar numbers | High | Never displayed in full; store hashed/tokenized, mask in UI |
| Household member details (names, ages, relations) | High | Owner-only access; never shown to other citizens or on public maps |
| Contact details of former owners | High | Retained for record purposes only, access-restricted, not publicly listed |

## 3. Aadhaar Handling Principles
- Aadhaar numbers should **never be stored or displayed in plaintext** in the application layer — only a verified linkage token/hash should be retained, in line with UIDAI guidelines.
- Any Aadhaar verification should go through UIDAI-approved e-KYC APIs, not custom validation logic.
- "Unlinking" a former owner's Aadhaar (as shown in the Joint Ownership module) must be a formally logged, irreversible action tied to a verified share-transfer/sale event — not a simple database delete.

## 4. Data Integrity & Auditability
- All ownership changes (registrations, share transfers, sales) should be recorded as **append-only ledger entries** — never overwritten or deleted — so the full history remains auditable (see `Data-Flow.md`).
- Consider a tamper-evident mechanism (cryptographic hashing or blockchain-backed ledger, see `Future-Scope.md`) so historical records cannot be silently altered.

## 5. Household & Personal Data Minimization
- The prototype already includes a disclaimer that household data is illustrative and not from a live civil registry — this principle should carry forward: **collect only what is strictly necessary** for the ULPIN/ownership use case, and avoid storing unrelated personal details.
- Household member data (names, ages, relations) should be encrypted at rest and accessible only to the owning household and authorized officials with a documented reason.

## 6. Infrastructure Security (Production)
- All API traffic over HTTPS/TLS.
- Encryption at rest for the database, especially for Aadhaar-linked and household tables.
- Rate limiting and anomaly detection on the ULPIN lookup and valuation APIs to prevent bulk scraping of ownership data.
- Regular security audits and penetration testing before any integration with real government data sources.

## 7. Compliance Considerations
A production version of this system would need to align with:
- **UIDAI Aadhaar Act & Regulations** for any Aadhaar-linked functionality.
- **Digital Personal Data Protection Act (DPDP), 2023** (India) for handling citizens' personal and household data.
- Relevant **state Registration Department** data-sharing and privacy policies, since land records are state-subject matter in India.

## Disclaimer
This document describes the intended security posture for a real deployment. The current repository is a **prototype/demo only**, uses no real personal data, and should not be treated as production-ready or security-audited software.
