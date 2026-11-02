# Lab Setup

## Infrastructure
- Domain Controller: Windows Server 2019 on GCP (us-central1-a)
- Domain: lab.local
- Attacker: Kali Linux on VMware Fusion (Mac M1)

## Users Created
- 10 regular users (jsmith, asmith, bjones, mwilson, ktaylor, rmartin, ljohnson, pwhite, slee, dmoore)
- Password: Password123 (intentionally weak for password spraying simulation)
- svc_sql: service account with SPN MSSQLSvc/dc01.lab.local:1433 (Kerberoasting target)
- labadmin: Domain Admin account (Pass-the-Hash target)

## Logging Enabled
- Credential Validation auditing
- Kerberos Authentication Service auditing
- Kerberos Service Ticket Operations auditing
- Logon auditing (success + failure)
- Account Lockout auditing
- Sysmon v15.22 with SwiftOnSecurity config

## Key Event IDs to watch
- 4625: Failed logon (password spraying)
- 4769: Kerberos service ticket request (Kerberoasting)
- 4624: Successful logon (Pass-the-Hash)
