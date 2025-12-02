# Red Team Reconnaissance Phase

## Objective

Identify exposed services, authentication mechanisms, directory access controls, and protocol behavior without credentials.

The goal was not exploitation — the goal was understanding exposure.



## Phase 1 — Connectivity Verification

Basic reachability checks confirmed the attacker VM can communicate with the Domain Controller.

If this step failed, nothing else would matter.

Connectivity confirms:

- Firewall allows traffic
- Domain visibility exists
- Attack surface exposure is real

## Evidence

![Ping](./ping.png)



## Phase 2 — Network Enumeration

A targeted scan was executed against domain protocol ports.

Open services included:

- Kerberos (authentication)  
- LDAP (directory queries)  
- SMB (file and policy distribution)  
- RPC (domain operations)  
- Global Catalog (forest-wide queries)

No unexpected services were found.

This means:
- The server is not misconfigured  
- No exposed dev services  
- No unnecessary open ports

## Evidence

![NMap](./nmap.png)



## Phase 3 — LDAP Observation

Anonymous LDAP queries returned directory metadata:

- Naming Contexts  
- Domain Name  
- Forest Name  
- Server Capabilities  
- Schema references  

However:

- User objects were blocked  
- Group membership retrieval was denied  
- Sensitive attributes were protected

This indicates:
- LDAP root disclosure exists
- Object enumeration is restricted

Typical corporate behavior.

## Evidence

![LDAP](./ldap.png)



## Phase 4 — Kerberos Validation

Tests were performed to identify accounts without pre-authentication.

Results indicated:

- All users enforce Kerberos pre-auth  
- No AS-REP hashes returned  
- Disabled users returned proper error codes  
- Invalid usernames were rejected properly  

This confirms strong Kerberos posture.



## Final Assessment

The domain resists unauthenticated enumeration and ticket harvesting.

From an attack perspective:
- Initial compromise is unlikely
- Credential theft paths are closed
- Lateral movement would require phishing or internal compromise



## Risk Level

Low exposure at perimeter authentication level.



## Recommendation

Continue enforcement of:

- Kerberos pre-authentication  
- LDAP ACL controls  
- Audit authentication failures regularly  

