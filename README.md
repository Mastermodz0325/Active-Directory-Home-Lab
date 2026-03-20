Active Directory Home Lab

Windows Server 2022 | Windows 10 | VirtualBox | DNS | GPO | RSAT

Overview

Built a virtualized Active Directory environment to simulate real-world helpdesk and junior system administration tasks. This lab focuses on identity management, access control, Group Policy, and troubleshooting common domain issues.

Environment

Hypervisor: VirtualBox

Domain Controller: Windows Server 2022

Client Machine: Windows 10

Domain: mylab.local

Core Services: Active Directory Domain Services (AD DS), DNS

Admin Tools: ADUC, Group Policy Management, DNS Manager, RSAT

Key Implementations

Promoted Windows Server 2022 to a Domain Controller

Created and configured the mylab.local domain

Configured DNS with forwarders for external resolution

Joined a Windows 10 client to the domain

Created users and security groups

Implemented group-based access control for shared folders

Configured NTFS + share permissions

Created and applied a Workstation Lockdown GPO

Installed RSAT for remote administration

Delegated password reset permissions to a helpdesk user (jhelpdesk)

Troubleshooting Experience

Resolved multiple real-world issues encountered during setup:

DNS Resolution Failure

Impact: Domain join/login instability

Fix: Corrected DNS configuration and forwarders

Virtual Network Misconfiguration (NAT)

Impact: Client unable to communicate with Domain Controller

Fix: Adjusted network adapter settings and IP configuration

Permissions & Access Issues

Impact: Users unable to access shared folders

Fix: Corrected NTFS vs Share permission alignment and inheritance

Group Membership Not Applying

Impact: Access changes not taking effect

Fix: Forced group policy refresh and token update

Delegation Validation

Impact: Helpdesk user initially unable to reset passwords

Fix: Correctly applied delegated permissions in ADUC

Skills Demonstrated

Active Directory Administration

DNS Configuration & Troubleshooting

Windows Domain Environments

Group Policy Management (GPO)

NTFS & Share Permissions

Role-Based Access Control (RBAC)

RSAT / Remote Administration

Windows Troubleshooting Methodology

Screenshots

Domain Controller Setup

AD Users and Computers

Domain-Joined Client

Group Policy Configuration

Shared Folder Permissions

Helpdesk Delegation

Key Takeaways

DNS is critical to Active Directory functionality and authentication

Group-based permissions are more scalable than user-based access

Proper delegation reduces reliance on Domain Admin accounts

Troubleshooting is as important as initial configuration

Next Steps

Implement Organizational Units (OUs) with department-based policies

Automate user provisioning with PowerShell

Deploy login scripts and drive mappings

Enable auditing and monitor security logs

Simulate helpdesk ticket scenarios

Repository Structure
active-directory-homelab/
├── README.md
├── screenshots/
├── diagrams/
├── docs/
├── scripts/
└── notes/
Why This Project Matters

This lab replicates core tasks performed in entry-level IT roles, including helpdesk support and junior system administration. It demonstrates hands-on experience with user management, access control, policy enforcement, and troubleshooting in a Windows domain environment.
