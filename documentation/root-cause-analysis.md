# Root Cause Analysis

#### Investigation identified Event ID 4740 on DC01.

#### Caller Computer Name:
### CLIENT01

Further investigation found a persistent mapped drive configured with outdated credentials. These incorrect credentials repeatedly attempted authentication against Active Directory, triggering account lockout policies.
