# Troubleshooting Log

## Overview
This document captures real issues encountered while building the Active Directory lab, along with the diagnostic process and resolutions. These scenarios reflect common helpdesk and system administration tasks in Windows domain environments.

---

## Issue 1 — DNS Resolution Failure

### Symptoms
- Client unable to reliably join domain  
- Login delays or failures  
- ping mylab.local failed  

### Diagnosis
- Checked client IP configuration using ipconfig /all  
- Identified incorrect DNS server assignment  

### Root Cause
- Client machine was not pointing to the Domain Controller for DNS  

### Resolution
- Set client DNS server to Domain Controller IP  
- Verified resolution using nslookup mylab.local  

### Result
- Domain join and authentication worked successfully  

### Key Lesson
- Active Directory depends heavily on proper DNS configuration  

---

## Issue 2 — VirtualBox Networking Misconfiguration

### Symptoms
- Client unable to communicate with Domain Controller  
- Ping requests failed  

### Diagnosis
- Reviewed VirtualBox network adapter settings  
- Checked IP addressing and subnet alignment  

### Root Cause
- Incorrect NAT/adapter configuration prevented communication  

### Resolution
- Reconfigured network adapter settings in VirtualBox  
- Ensured both machines were on the same network  

### Result
- Successful communication between client and Domain Controller  

### Key Lesson
- Domain environments require proper network communication between systems  

---

## Issue 3 — Shared Folder Access Denied

### Symptoms
- User unable to access shared folder  
- “Access Denied” error  

### Diagnosis
- Reviewed NTFS and share permissions  
- Compared user group membership against assigned permissions  

### Root Cause
- Misalignment between NTFS and share permissions  

### Resolution
- Reconfigured permissions using group-based access control  
- Ensured proper inheritance settings  

### Result
- User successfully accessed shared resources  

### Key Lesson
- Effective access is determined by BOTH NTFS and share permissions  

---

## Issue 4 — Group Membership Not Applying

### Symptoms
- User added to group but access not granted  
- Permission changes not reflected  

### Diagnosis
- Verified group membership in Active Directory  
- Checked user session state  

### Root Cause
- Security token not updated after group change  

### Resolution
- Ran gpupdate /force  
- Logged user out and back in  

### Result
- Group permissions applied correctly  

### Key Lesson
- Group membership changes require a token refresh (logoff/logon or policy update)  

---

## Issue 5 — Helpdesk Delegation Not Working

### Symptoms
- Helpdesk user (jhelpdesk) unable to reset passwords  

### Diagnosis
- Reviewed delegated permissions in Active Directory  
- Verified scope and OU targeting  

### Root Cause
- Delegation not properly configured or scoped  

### Resolution
- Reconfigured using Delegate Control Wizard  
- Assigned password reset permissions correctly  

### Result
- Helpdesk user successfully reset passwords  

### Key Lesson
- Delegation must be correctly scoped and validated to function properly  

---

## Summary

This project involved building and troubleshooting a Windows-based Active Directory environment in a virtualized lab setting. Multiple real-world issues were identified, diagnosed, and resolved using standard system administration tools and methodologies.

---

### DNS Configuration & Troubleshooting
- Resolved name resolution issues impacting domain join and authentication  
- Verified DNS functionality using ipconfig and nslookup  

---

### Network Connectivity
- Diagnosed VirtualBox networking issues affecting client-to-server communication  
- Corrected adapter configuration to restore connectivity  

---

### Access Control & Permissions
- Configured and troubleshot NTFS and share permissions  
- Implemented group-based access control (RBAC)  

---

### Active Directory Group Behavior
- Identified delays in permission application due to token caching  
- Resolved using gpupdate and session refresh  

---

### Delegated Administration
- Configured helpdesk-level permissions using least privilege principles  
- Validated password reset capabilities  

---

## Final Outcome

This project demonstrates hands-on experience with core helpdesk and junior system administration tasks, including identity management, access control, policy enforcement, and troubleshooting in a Windows domain environment.
