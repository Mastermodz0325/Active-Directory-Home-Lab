Troubleshooting Log
Overview

This document captures real issues encountered while building the Active Directory lab, along with the diagnostic process and resolutions. These scenarios reflect common helpdesk and system administration tasks in Windows domain environments.

Issue 1 — DNS Resolution Failure

Symptoms

Client unable to reliably join domain

Login delays or failures

ping mylab.local failed

Diagnosis

Checked client IP configuration using ipconfig /all

DNS server was not pointing to Domain Controller

Root Cause

Incorrect DNS configuration on client machine

Resolution

Set client DNS server to Domain Controller IP

Verified with nslookup mylab.local

Result

Domain join and authentication functioned correctly

Key Lesson

Active Directory heavily depends on proper DNS configuration

Issue 2 — VirtualBox Networking Misconfiguration

Symptoms

Client unable to communicate with Domain Controller

Ping requests failed

Diagnosis

Verified network adapter settings in VirtualBox

Checked IP addressing scheme

Root Cause

Incorrect NAT/adapter configuration preventing communication

Resolution

Adjusted VirtualBox network settings

Ensured both machines were on the same network

Result

Successful communication between client and Domain Controller

Key Lesson

Network configuration must allow direct communication for domain environments

Issue 3 — Shared Folder Access Denied

Symptoms

User unable to access shared folder

“Access Denied” error

Diagnosis

Reviewed share permissions and NTFS permissions

Compared assigned groups vs user membership

Root Cause

Misalignment between NTFS and share permissions

Resolution

Updated permissions to use group-based access

Ensured correct inheritance settings

Result

User successfully accessed shared folder

Key Lesson

Effective access is determined by BOTH NTFS and share permissions

Issue 4 — Group Membership Not Applying

Symptoms

User added to group but access not granted

Permissions changes not reflected

Diagnosis

Checked group membership in AD

Verified login session timing

Root Cause

Security token not updated after group change

Resolution

Forced update using:

gpupdate /force

Logged user out and back in

Result

Group permissions applied correctly

Key Lesson

Group membership changes require token refresh (logoff/logon or gpupdate)

Issue 5 — Helpdesk Delegation Not Working

Symptoms

Helpdesk user (jhelpdesk) unable to reset passwords

Diagnosis

Reviewed delegated permissions in Active Directory

Verified correct OU scope

Root Cause

Delegation not properly applied or scoped

Resolution

Reconfigured delegation using “Delegate Control Wizard”

Assigned password reset permissions

Result

Helpdesk user successfully reset user passwords

Key Lesson

Delegation must be correctly scoped and assigned to function properly

Summary

This troubleshooting experience reinforced key system administration concepts including:

DNS as a core dependency for Active Directory

Importance of proper network configuration

Interaction between NTFS and share permissions

Security group propagation behavior

Delegation and least privilege principles
