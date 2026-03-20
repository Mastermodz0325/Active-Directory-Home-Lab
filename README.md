### 💻 Client Machine Integration
- Deployed Windows 10 VM  
- Joined client to domain  
- Verified domain authentication  
- Troubleshot domain join and login issues  

---

### 🔐 Group Policy (GPO)
- Created custom GPO: **Workstation Lockdown Policy**  
- Restricted Control Panel and system settings  
- Applied security filtering to target specific users  
- Used `gpupdate /force` to apply policies  

---

### 📁 File Server & Permissions
- Created shared folder with NTFS and Share permissions  
- Implemented group-based access control (`FileShare_RW`)  
- Disabled inheritance to secure resources  
- Resolved permission conflicts  

---

### 👨‍💼 Delegation (Helpdesk Simulation)
- Delegated password reset permissions to `jhelpdesk`  
- Installed RSAT tools on client machine  
- Managed users remotely using `dsa.msc`  
- Simulated real helpdesk workflows  

---

### 🌐 Networking
- Configured dual network adapters (Internal + NAT)  
- Enabled internet access while maintaining domain connectivity  
- Diagnosed network vs DNS issues  

---

## 🛠️ Troubleshooting & Issues Resolved

### ❌ DNS Resolution Failure
- Issue: `nslookup` timeouts  
- Fix: Configured DNS forwarders and corrected DC DNS settings  

---

### ❌ No Internet Access in Lab
- Issue: RSAT installation failed (`0x8024402c`)  
- Fix: Added NAT adapter for outbound connectivity  

---

### ❌ Permission Issues
- Issue: Unauthorized access to shared folder  
- Fix: Disabled inheritance and used group-based permissions  

---

### ❌ Group Membership Not Applying
- Issue: Access denied despite correct group membership  
- Fix: Log out/in to refresh authentication token  

---

### ❌ GPO Over-Restriction
- Issue: Helpdesk user unable to access Settings  
- Fix: Adjusted GPO security filtering  

---

### ❌ RSAT Installation Failure
- Issue: Feature not installing  
- Fix: Resolved DNS + network configuration  

---

## 🚀 Skills Demonstrated

- Active Directory Administration  
- DNS Configuration & Troubleshooting  
- Group Policy Management  
- Windows Server Administration  
- Network Troubleshooting  
- Access Control & Permissions (NTFS + Share)  
- Helpdesk Operations Simulation  
- Virtualization (VirtualBox)  

---

## 🔧 Future Improvements

- Implement Organizational Units (OUs)  
- Add second client machine for multi-user simulation  
- Configure drive mapping via GPO  
- Implement audit policies (logon tracking)  
- Add DHCP server role  
- Simulate multi-domain or multi-DC environment  

---

## 📸 Screenshots (Coming Soon)
- Domain Controller setup  
- Active Directory Users and Groups  
- Group Policy configuration  
- Shared folder permissions  
- Client domain login  

---

## 💡 Key Takeaway

This project goes beyond basic setup by simulating real-world IT scenarios, including troubleshooting DNS failures, permission conflicts, and network configuration issues commonly encountered in enterprise environments.
