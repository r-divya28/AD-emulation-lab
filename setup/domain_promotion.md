# Domain Promotion and Forest Creation

## Objective

Promote the server from a standalone Windows machine into a Domain Controller and create a new Active Directory forest.

This action converted the host from a general-purpose server into:

- Authentication authority  
- Credential database  
- Domain policy engine  
- Central identity lifecycle system  



## Domain Definition

The following parameters were selected:

- Forest name: mydomain.local  
- Integrated DNS service  
- Global Catalog enabled  
- Directory Services Recovery Mode configured  



## What Happens During Promotion

Internally, this process performs:

- Creation of NTDS database  
- Initialization of SYSVOL  
- Installation of Kerberos services  
- Registration of LDAP endpoints  
- Activation of DNS zones  
- Establishment of replication engine  

The system becomes the root trust boundary of the environment.



## Evidence

(Insert Screenshot Here)



## Security Perspective

This stage marks the biggest security shift:

Before:
- One compromised host

After:
- One compromised domain = total compromise

The Domain Controller now contains:

- User hashes  
- Trust relationships  
- Group membership data  
- Password policies  
- Authentication secrets  

Logging into this machine means compromising everything.



## Risk Classification

Privilege tier: Tier 0  
Impact level if breached: Critical



## Recommendation

Organizations should:

- Limit DC interactive logins  
- Monitor Kerberos logs  
- Separate admin tiers  
- Enforce logging centrally  
- Harden network access first at the DC layer  
