# Domain User Creation

## Purpose

A standard domain user account was created to simulate a real employee identity.  
This account was used for:

- Authentication testing  
- Policy validation  
- Group membership simulation  
- Permission modeling  



## User Created

Username: alice  
Domain: mydomain.local  
Role: Standard user



## Why This Matters

Enterprise environments are built around identity, not machines.

Each user identity represents:

- A potential attack path  
- A policy enforcement target  
- A privileged boundary  

Creating controlled test users allows behaviors like:

- Authentication  
- Kerberos ticket generation  
- Policy inheritance  
- Account status handling  

to be tested safely and realistically.



## Evidence

![ ](./user.png)



## Security Perspective

Improper user management causes:

- Privilege creep  
- Account misuse  
- Orphaned identities  
- Access overspill  

Well-managed identity systems:

- Reduce exposure  
- Improve traceability  
- Enable strong governance  



## Recommendation

Organizations should:

- Enforce strict life-cycle management  
- Rotate passwords periodically  
- Disable unused accounts  
- Audit identity usage quarterly  

