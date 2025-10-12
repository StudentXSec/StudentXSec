**Lab Title:** Microsoft Entra ID – Create, Configure, and Manage Groups  
**Author:** Chris (Xavier) Charles — StudentXSec Labs  
**Date Executed:** 2025-10-13  
**Lab Environment:** StudentXSecurity.onmicrosoft.com (Business Tenant)  
**IAM Role Used:** Global Administrator (Admin@StudentXSecurity.onmicrosoft.com)  
**Framework Alignment:** NIST 800-53 AC-2 (Account Management), AC-3 (Access Enforcement)  
**Tools & Platforms:** Microsoft Entra ID (Azure AD)  
**Lab Type:** IAM / Access Governance  
**Version:** v1.0  
---

## 📑 Table of Contents
- [🎯 Objective](#-objective)
- [🧰 Tools & Environment](#-tools--environment)
- [🧠 Key Skills Practiced](#-key-skills-practiced)
- [🧾 Steps Performed](#-steps-performed)
- [📑 Results Summary](#-results-summary)
- [💡 Key Takeaways](#-key-takeaways)
- [🧩 Evidence Files](#-evidence-files)
- [📚 Framework Reference](#-framework-reference)
- [🧾 Change History](#-change-history)

---

## 🎯 Objective
Create and configure a **Microsoft 365 group** in Microsoft Entra ID to represent the **Northwest Sales** team.  
This lab demonstrates how to manually create collaboration-enabled groups, assign ownership and membership, and verify their presence within the Entra environment.

---

## 🧰 Tools & Environment
- Microsoft Entra Admin Center → [https://entra.microsoft.com](https://entra.microsoft.com)  
- Tenant: `StudentXSecurity.onmicrosoft.com`  
- Role: Global Administrator  
- License: Microsoft Entra ID P1 + Microsoft 365 Business Basic (Trial)

---

## 🧠 Key Skills Practiced
- Creating **Microsoft 365 Groups** for collaboration  
- Assigning **group ownership** and **membership**  
- Understanding group propagation delays and verification methods  
- Reinforcing access governance through proper group setup

---

## 🧾 Steps Performed

### Step 1 – Create the Microsoft 365 Group “Northwest Sales”
1. Navigate to **Microsoft Entra Admin Center → Identity → Groups → All Groups → + New Group**.  
2. Enter the following details:  
   - **Group type:** Microsoft 365  
   - **Group name:** Northwest Sales  
   - **Membership type:** Assigned  
   - **Owner:** Admin@StudentXSecurity.onmicrosoft.com  
   - **Member:** Chris Green  
3. Review the configuration before creating the group.  

**Screenshot – Group Creation Form:**  
![New Group creation form showing Northwest Sales details](./screenshots/group_northwest_creation_form.png)

4. Click **Create** and wait for confirmation.  
5. Refresh the **All Groups** list several times until the new group appears.  

**Screenshot – All Groups View:**  
![All Groups list showing Northwest Sales group created successfully](./screenshots/group_northwest_list.png)

---

## 📑 Results Summary
| Task | Action | Verified |
|------|---------|-----------|
| Create Microsoft 365 Group | Northwest Sales created successfully | ✅ |
| Assign Owner | Admin@StudentXSecurity.onmicrosoft.com assigned | ✅ |
| Assign Member | Chris Green assigned | ✅ |
| Verify Group | Appears in All Groups list | ✅ |

---

## 💡 Key Takeaways
- Confirmed how to create **Microsoft 365 collaboration groups** for departmental access.  
- Learned to assign ownership and membership during group creation.  
- Verified how new groups may take several refresh cycles to appear in Entra ID.  
- Reinforced documentation and evidence tracking standards.

---

## 🧩 Evidence Files
All visual proof captured as embedded screenshots within this README.

| Type | File | Description |
|------|------|-------------|
| Screenshot | `group_northwest_creation_form.png` | Form showing Northwest Sales group setup |
| Screenshot | `group_northwest_list.png` | All Groups view verifying creation |

---

## 📚 Framework Reference
- **NIST 800-53:** AC-2 (Account Management), AC-3 (Access Enforcement)  
- **ISO/IEC 27001:** A.9 (Access Control)

---

## 🧾 Change History
| Version | Date | Changes |
|----------|------|----------|
| v1.0 | 2025-10-13 | Initial documentation for Northwest Sales group creation |

---

## 📚 Next Step
Continue to **Lab 02 – Configure and Manage Device Registration**  
to explore how Microsoft Entra ID supports device registration and management, including:

- Understanding Microsoft Entra Registered, Joined, and Hybrid Joined devices  
- Exploring BYOD (Bring Your Own Device) registration scenarios  
- Preparing for Conditional Access and Intune integration

📘 *This next section expands your IAM focus from user and group objects to device identities, connecting access governance with endpoint compliance.*


---

# 🖥️ Configure and Manage Device Registration
*(Continuation of Lab 02 – Microsoft Entra ID: Create, Configure, and Manage Groups)*

> This section explores how Microsoft Entra ID manages **device identities** in addition to user and group objects.  
> You’ll review **device registration settings**, understand the difference between **Entra Registered**, **Entra Joined**,  
> and **Hybrid Joined** devices, and see how these identities form the foundation for **Conditional Access** and  
> **Intune-based management** in future labs.

---
---
**Lab Title:** Microsoft Entra ID – Configure and Manage Device Registration  
**Author:** Chris (Xavier) Charles — StudentXSec Labs  
**Date Executed:** 2025-10-14  
**Lab Environment:** StudentXSecurity.onmicrosoft.com (Business Tenant)  
**IAM Role Used:** Global Administrator (Admin@StudentXSecurity.onmicrosoft.com)  
**Framework Alignment:** NIST 800-53 AC-2 (Account Management), AC-17 (Remote Access), IA-2 (Identification and Authentication)  
**Tools & Platforms:** Microsoft Entra ID, Windows 10/11 Settings, Intune (optional)  
**Lab Type:** IAM / Device Governance  
**Version:** v1.0  
---

## 📑 Table of Contents
- [🎯 Objective](#-objective)
- [🧠 Key Concepts](#-key-concepts)
- [🪜 Steps Performed](#-steps-performed)
- [📑 Results Summary](#-results-summary)
- [💡 Key Takeaways](#-key-takeaways)
- [🧩 Evidence Files](#-evidence-files)
- [📚 Framework Reference](#-framework-reference)
- [🧾 Change History](#-change-history)

---

## 🎯 Objective
Understand how Microsoft Entra ID registers and manages device identities, enabling secure access to organizational resources across **BYOD**, **corporate**, and **hybrid** environments.  
This lab demonstrates the difference between **Entra Registered**, **Entra Joined**, and **Hybrid Joined** devices and how these models support Conditional Access and MDM enforcement.

---

## 🧠 Key Concepts

| Device Type | Definition | Primary Audience | Key Capabilities |
|--------------|-------------|------------------|------------------|
| **Entra Registered** | Device registered to Entra ID without requiring organizational sign-in | BYOD / Personal Devices | SSO to cloud apps, Conditional Access, MDM via Intune |
| **Entra Joined** | Work device joined directly to Entra ID using org credentials | Cloud-first / Managed organizations | SSO to cloud and on-prem resources, MDM, Hello for Business |
| **Hybrid Joined** | Device joined to on-prem AD and registered with Entra ID | Hybrid enterprises | Unified management, Conditional Access, Group Policy integration |

---

## 🧾 Steps Performed

### Step 1 – Review Device Registration Settings
1. Navigate to **Microsoft Entra Admin Center → Identity → Devices → All Devices**.  
2. Observe any existing registered devices (if none appear, this is expected for new tenants).  
3. Capture the overview pane showing the **Device Settings** options at the top.  
📸 *Screenshot:* `screenshots/device_settings_overview.png`

---

### Step 2 – Explore Device Registration Options
1. In **Devices → Device Settings**, review:
   - Users may join devices to Microsoft Entra ID (Yes/No)  
   - Additional local administrators on joined devices  
   - Require Multi-Factor Authentication to join devices  
2. Document the default configuration and any adjustments you make.  
📸 *Screenshot:* `screenshots/device_registration_settings.png`

---

### Step 3 – Simulate BYOD Registration (Conceptual Demo)
*(No actual device enrollment required for this lab)*  
1. Open **Windows Settings → Accounts → Access Work or School → Connect**.  
2. Show how a user would enter their organization account (e.g., ChrisG@StudentXSecurity.onmicrosoft.com).  
3. Explain how this registers the device to Entra ID for SSO and Conditional Access.  
📸 *Screenshot:* `screenshots/byod_registration_walkthrough.png`

---

### Step 4 – Review Microsoft Entra Joined and Hybrid Joined Concepts
1. Document the differences between cloud-only join and hybrid join.  
2. Reference Intune or Configuration Manager as tools for policy enforcement.  
📸 *Screenshot:* `screenshots/device_join_models_summary.png`

---

## 📑 Results Summary
| Scenario | Description | Verified |
|-----------|--------------|-----------|
| Device Registration Settings Reviewed | Confirmed default Entra Device Settings | ✅ |
| BYOD Registration Simulated | Walked through Access Work or School flow | ✅ |
| Join Models Compared | Summarized Registered vs. Joined vs. Hybrid | ✅ |

---

## 💡 Key Takeaways
- Device identities extend IAM governance beyond user objects.  
- Entra Registered devices support BYOD with Conditional Access enforcement.  
- Entra Joined and Hybrid Joined models enable full enterprise device management and SSO.  
- Understanding device status is crucial for future labs covering Conditional Access and Intune integration.

---

## 🧩 Evidence Files
All evidence is captured as screenshots within this README.

| Type | File | Description |
|------|------|-------------|
| Screenshot | `device_settings_overview.png` | Entra Device Settings overview |
| Screenshot | `device_registration_settings.png` | Default device registration options |
| Screenshot | `byod_registration_walkthrough.png` | Simulated BYOD device enrollment window |
| Screenshot | `device_join_models_summary.png` | Comparison of device join models |

---

## 📚 Framework Reference
- **NIST 800-53:** AC-17 (Remote Access), IA-2 (Identification and Authentication)  
- **ISO/IEC 27001:** A.6.2 (Mobile Device and Teleworking Policy), A.9 (Access Control)  

---

## 🧾 Change History
| Version | Date | Changes |
|----------|------|----------|
| v1.0 | 2025-10-14 | Initial documentation of device registration concepts and settings review |
