# Future Scope

## 1. Real Backend & Database Integration
Move from the current client-only mock data to a real backend with a persistent database (see `System-Architecture.md`), so records survive beyond a single browser session and can be shared across users and departments.

## 2. Surveyed, As-Built 3D Geometry
Replace the current illustrative CSS/JS 3D concept model with true surveyed geometry — using drone photogrammetry, LiDAR scans, or BIM (Building Information Modeling) data — so the 3D model reflects the actual as-built structure, not a visual concept.

## 3. Integration with Real GIS & Government Systems
Connect to actual land record systems (e.g., DILRMP, state Registration Department databases, Bhoomi/SVAMITVA-style platforms) so plot boundaries, guideline values, and ownership data are sourced live rather than from a mock dataset.

## 4. Legal Recognition of Sub-Parcel ULPINs
Work with policy makers to formally define and legally recognize sub-parcel ULPINs for floors, units, and parking bays — so they carry the same legal weight as the base ULPIN and can be cited in sale deeds, loans, and disputes.

## 5. Aadhaar-Based Identity Verification
Replace the current simulated login with real Aadhaar-linked (or equivalent government ID) authentication and e-KYC, ensuring every ownership record is tied to a verified identity.

## 6. Mobile Application
Build native iOS/Android apps so citizens can use "Find My Plot" navigation and view their property records on the go, with offline caching for low-connectivity areas.

## 7. Blockchain-Backed Ownership Ledger
Explore a blockchain or similarly tamper-evident ledger for the ownership-history and share-transfer records, making the audit trail cryptographically verifiable and resistant to backdated tampering.

## 8. Automated Valuation Model (AVM) Improvements
Enhance the 10-year value projection engine with real transaction data, machine-learning-based price trend modeling, and live tracking of government project milestones (instead of static, indicative projections).

## 9. Drone/Satellite-Based Change Detection
Periodically compare satellite/drone imagery against registered building footprints to automatically flag unauthorized construction or deviations from the recorded 3D structure.

## 10. Multi-Language & Accessibility Support
Add regional language support (Tamil, Hindi, and others depending on deployment state) and accessibility improvements (screen-reader support, high-contrast mode) so the system is usable by all citizens, not just English speakers.

## 11. Dispute Resolution Workflow
Add a formal in-app workflow for flagging and resolving ownership disputes (e.g., overlapping claims on a sub-parcel), with document upload and status tracking, rather than requiring an entirely offline legal process.

## 12. Open API for Third-Party Integration
Expose a public, rate-limited API so banks (for loan verification), real estate platforms, and legal-tech tools can verify ULPIN and sub-parcel ownership data programmatically, with the citizen's consent.
