# Active Directory – Domain Local & Global Group Creation and Membership

Professional guide and reference for creating **Domain Local** and **Global** security groups in Active Directory Domain Services (AD DS), managing group membership, and following Microsoft best practices (AGDLP model).

## Overview

This repository documents how to create and manage the two most commonly used Active Directory group scopes:

| Scope            | Purpose                                      | Typical Use Case                          |
|------------------|----------------------------------------------|-------------------------------------------|
| **Global**       | Organize users/computers by role or department | Role-based groups (e.g. `GG-Sales-Team`) |
| **Domain Local** | Assign permissions to resources              | Resource groups (e.g. `DL-Sales-Share-Modify`) |

**Recommended model: AGDLP**
1. **A**ccounts → **G**lobal groups  
2. Global groups → **D**omain **L**ocal groups  
3. Domain Local groups → **P**ermissions on resources

## Prerequisites

- Domain Admin rights or delegated permissions to create/modify groups
- Active Directory Users and Computers (ADUC) **or** Active Directory PowerShell module
- Target Organizational Unit (OU) for groups (recommended)

```powershell
# Install / Import AD module if needed
Install-WindowsFeature RSAT-AD-PowerShell   # on Windows Server
Import-Module ActiveDirectory
