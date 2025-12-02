# Static IP Configuration – Domain Controller

## Objective

Ensure the Domain Controller operates with a fixed IP address to maintain consistent DNS resolution and Kerberos authentication behavior.

## Configuration Applied

- IP Address: 192.168.5.10  
- Subnet Mask: 255.255.255.0  
- Default Gateway: Not configured  
- Preferred DNS: Self (192.168.5.10)

## Security Rationale

Active Directory relies heavily on DNS. If a Domain Controller changes its IP due to DHCP, authentication and directory queries often fail. Kerberos tickets reference service locations; mismatches break trust relationships.

Using a static IP eliminates:

- DNS cache poisoning issues  
- Authentication failure scenarios  
- AD replication failures  
- Discovery instability  

## Evidence

![Static IP Configuration](./dc_static_ip.png)

## Result

The system now retains a deterministic network identity and can safely operate as a DNS and authentication authority.

## Risk Level

Low

## Recommendation

All Domain Controllers should use static IP addressing with restricted administrative modification rights.
