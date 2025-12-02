# Security Group Configuration

## Purpose

A security group was created to implement role-based access control (RBAC) principles.

Group-based access is the foundation of secure directory management.



## Group Created

Name: Employees-Group  
Type: Security  
Scope: Global  

User `alice` was added as a member.



## Why Groups Matter

Direct user permissions cause:

- Security sprawl  
- Lack of traceability  
- Manual overhead  
- Inconsistent privilege modelling  

Groups allow:

- Permission reuse  
- Centralized control  
- Simplified audits  
- Clean role enforcement  



## Evidence

![ ](./group.png)



## Security View

All permissions should be:

- Assigned to groups  
- Audited by role  
- Managed centrally  

Avoid assigning:

- File rights
- Share permissions
- Application access  

directly to individual users.



## Recommendation

Use groups for:

- Access control  
- Policy scoping  
- Compliance enforcement  
- Identity governance  

