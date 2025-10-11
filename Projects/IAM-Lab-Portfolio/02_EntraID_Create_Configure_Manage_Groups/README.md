**Lab Title:** Microsoft Entra ID – Create, Configure, and Manage Groups  
**Author:** Chris (Xavier) Charles — StudentXSec Labs  
**Date Executed:** 2025-10-12  
**Lab Environment:** StudentXSecurity.onmicrosoft.com (Business Tenant)  
**IAM Role Used:** Global Administrator (Admin@StudentXSecurity.onmicrosoft.com)  
**Framework Alignment:** NIST 800-53 AC-2 (Account Management), AC-3 (Access Enforcement)  
**Tools & Platforms:** Microsoft Entra ID  
**Lab Type:** IAM / Access Governance  
**Version:** v1.0  
---

## 📑 Table of Contents
- [🎯 Objective](#-objective)
- [🧰 Tools & Environment](#-tools--environment)
- [🧠 Key Skills Practiced](#-key-skills-practiced)
- [🪜 Steps Performed](#-steps-performed)
- [📑 Results Summary](#-results-summary)
- [💡 Key Takeaways](#-key-takeaways)
- [🧩 Evidence Files](#-evidence-files)
- [📚 Framework Reference](#-framework-reference)
- [🧾 Change History](#-change-history)

---

## 🎯 Objective
Demonstrate how to create, configure, and manage Microsoft Entra ID groups, including security and Microsoft 365 groups.  
This lab reinforces proper group design, membership management, and access governance for enterprise environments.

---

## 🧰 Tools & Environment
- Microsoft Entra Admin Center (`entra.microsoft.com`)  
- Microsoft 365 Admin Center (`admin.microsoft.com`)  
- Tenant: `StudentXSecurity.onmicrosoft.com`  
- Role: Global Administrator  

---

## 🧠 Key Skills Practiced
- Creating and configuring **Security** and **Microsoft 365** groups  
- Setting **assigned vs. dynamic** membership rules  
- Managing **group ownership** and **nested memberships**  
- Applying the **principle of least privilege** to group roles  
- Preparing groups for **access reviews** and **license-based provisioning**

---

## 🪜 Steps Performed
1. Create and configure Security and Microsoft 365 groups  
2. Define dynamic membership rules based on user attributes  
3. Add and remove members manually and via rules  
4. Assign ownership roles for delegated group management  
5. Review group settings and permissions for compliance

---

## 📑 Results Summary
| Task | Action | Verified |
|------|---------|-----------|
| Group creation | Security and M365 groups configured | ☐ |
| Dynamic rules | Successfully applied and validated | ☐ |
| Ownership | Delegated properly | ☐ |
| Compliance check | Reviewed settings | ☐ |

---

## 💡 Key Takeaways
- Reinforced understanding of Entra ID group types and membership options  
- Practiced dynamic rule syntax and verification  
- Prepared foundation for future labs (Conditional Access and Access Reviews)

---

## 🧩 Evidence Files
| Type | File | Description |
|------|------|-------------|
| Screenshot | `screenshots/user_created_list.png` | Proof of user creation |
| Artifact | `artifacts/user_export.csv` | Exported list for audit evidence |

---

## 📚 Framework Reference
This lab aligns with the following control families:
- **NIST 800-53:** AC-2 (Account Management), AC-3 (Access Enforcement)  
- **ISO/IEC 27001:** A.9 (Access Control), A.12.4 (Logging and Monitoring)

---

## 🧾 Change History
| Version | Date | Changes |
|----------|------|----------|
| v1.0 | [YYYY-MM-DD] | Initial lab documentation |
| v1.1 | [optional] | Updated screenshots and results |
