# AD-emulation-lab

**OVERVIEW**

This project demonstrates the complete setup, enumeration, and initial security assessment of a Windows Active Directory environment using offensive (Red Team) and defensive (Blue Team) techniques in a controlled lab environment.
The objective was to build a realistic corporate domain setup and perform:
   Domain configuration
   User and group management
   Group Policy configuration
   Attack surface identification
   Defensive validation using real system behavior
This project documents both successful attacks and blocked attack attempts, reflecting real-world environments where not all attacks work due to proper security configurations.

**LAB ARCHITECTURE**

| Role              | OS                  | IP Address   |
| ----------------- | ------------------- | ------------ |
| Domain Controller | Windows Server 2022 | 192.168.5.10 |
| Client Machine    | Windows 11          | 192.168.5.20 |
| Attacker Machine  | Kali Linux          | 192.168.5.30 |

**Network:**
All machines were on an isolated internal network
DNS configured manually
No internet access during attack phase
Static IP addressing used for full control

_**Phase 1 – Domain Controller Setup**_

     Static IP assigned
     Server renamed to DC01
     Active Directory Domain Services installed
     Domain created: mydomain.local
     DNS self-hosted on DC

_**Phase 2 – Windows Client Setup**_

     Static IP configured
     Domain join completed
     Authentication using domain administrator
     Verified domain connectivity

_**Phase 3 – Active Directory Configuration**_

**Organizational Units Created**
    Employees
    Admins
    Computers

**User Management**
    Created domain user: alice@mydomain.local
    Created security group: Employees-Group
    Added Alice to Employees-Group

_**Phase 4 – Group Policy Configuration**_

Created password policy:
    Password history: 5
    Maximum age: 45 days
    Minimum length: 8
Complexity evaluated later in Blue Team review
GPO linked successfully to the domain.

_**Phase 5 – Red Team Attack Phase**_

**1. Network Enumeration**
Nmap was used to identify exposed domain services.
Findings:
    Kerberos (88)
    LDAP (389)
    SMB (445)
    Global Catalog (3268)
    DC RPC services (135)
    DNS (53)
This confirms the system is a fully functional Domain Controller with correct service exposure.

**2. LDAP Enumeration**

Anonymous LDAP queries were tested.
Result:
    RootDSE information retrievable
    Domain structure leaks:
    DC name
    Forest name
    Site name
    LDAP services
User listing blocked without authentication

**3. Kerberos AS-REP Roasting Test**

Tool: Impacket GetNPUsers
Result:
    No vulnerable accounts
    Pre-authentication enforced
    Administrator secured
    Alice secured
    Unknown users correctly rejected
    Disabled users identified via Kerberos error codes

| Test                | Result                 |
| ------------------- | ---------------------- |
| AS-REP Roasting     | Not vulnerable         |
| LDAP anonymous bind | Partially allowed      |
| User enumeration    | Blocked                |
| SMB null session    | Blocked                |
| Kerberos hardening  | Correct                |
| Password policy     | Active                 |
| Group enforcement   | Configured             |
| Attack surface      | Exposed but controlled |


The following defensive controls were confirmed:
     Kerberos pre-authentication enforced
     SMB hardened
     RPC restricted
     LDAP secured
     Group Policy correctly applied
     Domain authentication enforced
     Password controls active

_**Learning Outcomes**_

    Built a functional enterprise Active Directory environment
    Practiced AD domain configuration
    Implemented group policies
    Performed enumeration from attacker perspective
    Evaluated domain hardening
    Understood Kerberos behaviors
    Analyzed security failures as valid findings
    Documented defensive protections

_**Disclaimer**_
All testing was conducted on systems I owned and configured inside an isolated lab environment.
No external systems were accessed.

_**Author**_
Divya R
Cybersecurity | Red Team | Active Directory
