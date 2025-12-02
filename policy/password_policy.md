
# Password Policy Configuration

## Purpose

Password policy was enforced using Group Policy to govern how credentials behave domain-wide.

This ensures:

- Users meet baseline security requirements  
- Password variations cannot repeat indefinitely  
- Credentials expire on schedule  



## Applied Policy Settings

- Minimum password length: 8 characters  
- Password history: 5  
- Maximum password age: 45 days  


## Why This Matters

Weak passwords remain the most exploited attack vector.

Common attacks include:

- Password spraying  
- Credential stuffing  
- Offline hash cracking  
- Brute-force attempts  

Passwords that never expire or are short enable compromise with trivial effort.



## Evidence

![Policy Config](./policy.png)



## Risk Analysis

Current configuration is better than default, but not enterprise-grade.

Minimum length of 8 is often:

- Cracked quickly  
- Guessable  
- Vulnerable to common wordlists  



## Recommendation

Increase baseline policy:

- Minimum length ≥ 12  
- Enforce complexity  
- Implement MFA for administrators  
- Monitor lockout trends  
