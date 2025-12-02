# Kerberos Hardening Assessment

## Overview

Kerberos controls authentication in Active Directory.  
If Kerberos is weak, the domain is weak.

This assessment evaluated whether Kerberos pre-authentication is enforced.



## What Was Tested

AS-REP roasting attempts were made to extract encrypted authentication tickets for offline cracking.

No users were returned as vulnerable.



## Meaning

All domain accounts correctly require:

- Pre-authentication checks  
- Ticket validation  
- Time-synchronised handshakes  

This eliminates anonymous ticket harvesting attacks.



## Practical Impact

Kerberos hardening protects against:

- Credential disclosure  
- Offline cracking  
- Replay attacks  
- Ticket abuse  



## Recommendation

Maintain:

- Pre-authentication  
- Event log monitoring  
- Kerberos failure alerting  
- Administrative tier separation  

