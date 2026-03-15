# GDPR Compliance Checklist: Resource Reservation System

This checklist evaluates the application's alignment with GDPR principles based on the provided technical specifications (Specs 1-10).

| GDPR Principle / Requirement | Status | Evidence / Implementation Detail | Skeptic's Audit Note |
| :--- | :---: | :--- | :--- |
| **Lawfulness & Transparency** | ✅ | System requires login/registration (Spec 2). Privacy Policy is linked at `/privacypolicy`. | Ensure the registration page includes a mandatory "I agree to the Privacy Policy" checkbox. |
| **Purpose Limitation** | ✅ | Data is collected solely for resource reservation (Spec 3, 6, 7). | Verify that data isn't being repurposed for marketing without separate consent. |
| **Data Minimization** | ⚠️ | Only "Identity" and "Age" (for 15+ check) are collected (Spec 6). | To truly minimize, the system should only store a "True/False" flag for age verification rather than a birthdate. |
| **Accuracy** | ✅ | Users/Admins can modify reservations (Spec 4). | Admin power to modify (Spec 4) should be audited to prevent unauthorized changes to personal records. |
| **Storage Limitation** | ✅ | Administrator can delete reservers (Spec 5). | Deletion must be a "Hard Delete" from the database to comply with the Right to Erasure (Art. 17). |
| **Integrity & Confidentiality** | ✅ | Public view hides identity (Spec 8). | **Risk Check:** Check if "Resource Name" + "Time" could inadvertently identify a user in a small organization. |
| **Protection of Minors** | ⚠️ | System allows 15-year-olds (Spec 6). | GDPR Art. 8 default is 16. We must confirm if the local jurisdiction allows 15 as the age of digital consent. |
| **Privacy by Design (PbD)** | ✅ | System provider claims PbD (Spec 10). | This is a high-level claim; as a pentester, I would verify this via database encryption and secure session handling. |

---
*Audit conducted by: Novice Penetration Tester*
