# Organizational Unit Design

## Purpose

Organizational Units (OUs) were created to structure directory objects in a way that reflects real enterprise directory design.  
Rather than keeping all objects in default containers, custom OUs were designed to allow:

- Policy targeting  
- Delegated control  
- Cleaner audits  
- Logical separation of responsibilities  

---

## OU Structure Implemented

Three organizational units were created:

- Employees  
- Admins  
- Computers  

Each OU was designed to represent a real operational boundary inside an organization.

---

## Design Logic

### Employees OU
Designed to hold all standard user accounts.  
This allows:

- Enforcement of user-level policies  
- Simpler password policy targeting  
- Audit filtering  
- Bulk policy administration  

### Admins OU
Dedicated OU for privileged users.  
Separating administrative identities from standard employees ensures:

- Stronger control over domain privileges  
- Easier monitoring of privileged usage  
- Reduced risk of accidental policy inheritance  

### Computers OU
Workstations and devices are placed separately to:

- Apply endpoint-specific GPOs  
- Manage machine-level security  
- Control device identity independently from users  

---

## Evidence

(Insert screenshot)

---

## Security Consideration

Leaving objects in default system containers makes:

- Delegation impossible
- Misconfiguration more likely
- Auditing harder
- Privilege exposure easier

Proper OU design is foundational for secure Active Directory administration.

---

## Recommendation

Enterprises should:

- Never rely on default containers  
- Build OU hierarchy early  
- Separate administrator accounts explicitly  
- Delegate privileges at OU level  

