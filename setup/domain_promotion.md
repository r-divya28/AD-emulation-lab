# Domain Promotion

## Objective

Convert the Windows Server instance into the root authority for the enterprise domain.

## Domain Parameters

- Forest root: mydomain.local  
- Global catalog enabled  
- DNS installed locally  
- Directory Services Recovery Mode enabled  

## Operational Impact

The server transitions from a standalone machine to:

- Authentication authority  
- Credential store  
- Ticket-granting service  
- Directory services provider  
- Centralized identity system  

## Evidence

![Domain Promotion](./domain_promotion.png)

## Result

Forest creation succeeded with no warnings or configuration errors.

## Risk Considerations

This step introduces new risk exposure:

- Credential theft impact becomes high  
- Compromising DC = compromising domain  

## Recommendation

Restrict Domain Admin membership and log DC authentication carefully.

