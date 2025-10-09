# Microsoft Entra ID Lab – Assign Licenses to Users

## 🎯 Objective
Perform identity-lifecycle operations in Microsoft Entra ID:
- Create and manage users and security groups
- Assign group-based licenses in Microsoft 365
- Restore deleted users to simulate account recovery

---

## 🧰 Tools & Environment
- Microsoft Entra Admin Center  
- Microsoft 365 Admin Center  
- Role: User Administrator  
- Trial Azure Tenant (Free Sandbox)

---

## 🧠 Skills Practiced
- User provisioning & group management  
- Group-based license assignment  
- Role-based access control (RBAC)  
- Account deletion and restoration  
- Documentation for audit evidence  

---

## 🪜 Steps Performed

### 1️⃣ Create User – *Chris Green*
1. **Path:** Identity → Users → All Users → + New User  
2. Entered UPN `ChrisG`, Name `Chris Green`, temporary password.  
3. Verified account appeared in user list.  

📸 `screenshots/user_created_list.png`

---

### 2️⃣ Create Security Group – *Marketing*
1. **Path:** Identity → Groups → All Groups → + New Group  
2. Settings: Type = Security  |  Membership = Assigned  |  Owner = Admin  |  Member = Chris Green  
3. Verified new group in list.  

📸 `screenshots/group_creation_form.png`  
📸 `screenshots/group_membership_view.png`

---

### 3️⃣ Assign License to Group
1. **Path:** M365 Admin Center → Billing → Licenses  
2. Selected available license (E5 trial) → Groups → + Assign License → **Marketing**  
3. Confirmed success notification.  

📸 `screenshots/license_assignment_group.png`  
📸 `screenshots/license_success_message.png`

---

### 4️⃣ Delete & Restore User
1. Deleted Chris Green from All Users.  
2. Navigated to Deleted Users and restored account within retention window.  
3. Verified account reappeared with original attributes.  

📸 `screenshots/deleted_user_list.png`  
📸 `screenshots/user_restored.png`

---

## 📑 Results Summary
| Task | Action | Verified |
|------|---------|-----------|
| User Created | Chris Green visible in portal | ✅ |
| Security Group Created | Marketing + member assigned | ✅ |
| License Assigned | License applied to group | ✅ |
| User Restored | Account reinstated | ✅ |

---

## 💡 Key Takeaways
- Practiced full identity lifecycle: create → assign → license → delete → restore.  
- Learned group-based licensing simplifies access provisioning.  
- Reinforced audit documentation habits (screenshots + CSV exports).  
- Understood how Entra ID integrates with M365 for license governance.  

---

## 📚 Next Step
Continue to **Lab 02 – Secure Identities with Conditional Access** to apply policy-driven access control.
