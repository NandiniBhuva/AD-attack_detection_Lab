# Attacker Machine Setup

## Infrastructure
- kali-attacker VM: Debian 12 on GCP (10.128.0.4)
- Same internal network as DC (10.128.0.3)
- Confirmed connectivity via ping (0% packet loss)

## Tools Installed
- Impacket 0.14.0 — AD protocol toolkit (Kerberoasting, PtH)
- Kerbrute v1.0.3 — Kerberos password spraying
- NetExec 1.5.1 — SMB/LDAP attack framework (Pass-the-Hash)

## Tool Locations
- Impacket: ~/impacket-env/ (virtual environment)
- Kerbrute: ~/kerbrute
- NetExec: installed in impacket-env, run as `nxc`
