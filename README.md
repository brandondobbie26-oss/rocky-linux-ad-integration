# 🚀 Rocky Linux 9.6 Server Integration with Windows Active Directory and cPanel

## 📘 Project Overview

This project demonstrates a complete **end-to-end deployment** of a **Rocky Linux 9.6** server with **cPanel/WHM**, integrated into a **Windows Server 2022 Active Directory domain** (`itnexttech.com`).  
It represents a realistic enterprise-grade environment for hosting, authentication, and centralized management across Linux and Windows systems.

---

## 🎯 Project Objectives

### **Primary Objective**
Deploy and configure a **production-ready Rocky Linux 9.6** server with **cPanel/WHM** and integrate it into the **Active Directory (AD)** domain for centralized authentication and management.

### **Secondary Objectives**

| # | Objective | Description |
|---|------------|--------------|
| 1 | **Install and configure Rocky Linux 9.6** | Perform a clean OS setup, update system packages, and verify connectivity. |
| 2 | **Assign Static IP and Hostname** | Configure persistent network identity for server recognition and AD joining. |
| 3 | **Install cPanel & WHM** | Install using the official installer and verify web access to WHM. |
| 4 | **Integrate with Active Directory** | Join the Rocky Linux server to `itnexttech.com` using realmd, sssd, and kerberos. |
| 5 | **DNS and NTP configuration** | Ensure name resolution and time sync between AD and Linux. |
| 6 | **Automatic home directories** | Enable `oddjob-mkhomedir` for domain logins. |
| 7 | **Secure authentication** | Implement AD-based logins for admins and users. |
| 8 | **cPanel Mail Server setup** | Configure Exim, Dovecot, and DNS (MX, SPF, DKIM). |
| 9 | **Error handling and documentation** | Log every issue, command, and resolution. |
| 10 | **GitHub documentation** | Maintain live documentation with all updates and logs. |

---

## 🧩 Project Scope & Tools

| Category | Tool / Service | Purpose |
|-----------|----------------|----------|
| **Operating System** | Rocky Linux 9.6 | Core server OS |
| **Control Panel** | cPanel & WHM | Web hosting and management |
| **Authentication** | Windows Server 2022 AD | Domain controller |
| **Integration Tools** | realmd, sssd, krb5, samba-common, oddjob | Domain join and auth |
| **Mail Services** | Exim, Dovecot, Roundcube | Local mail system |
| **Time Sync** | chronyd | NTP synchronization |
| **Version Control** | GitHub | Documentation and tracking |
| **Virtualization** | VMware Workstation 17 | Test environment |

---

---

## 🪜 Step Tracking Checklist

- [ ] Install Rocky Linux 9.6 on VMware or physical machine  
- [ ] Configure Static IP and DNS  
- [ ] Set hostname (`rocky01.itnexttech.com`)  
- [ ] Verify connectivity (ping DC01 and internet)  
- [ ] Install cPanel and verify WHM login  
- [ ] Join Windows Active Directory (`itnexttech.com`)  
- [ ] Verify authentication using `realm list` and `id user@itnexttech.com`  
- [ ] Configure mail services and DNS records  
- [ ] Test internal and external email delivery  
- [ ] Push logs and screenshots to GitHub  

---

## 🧾 Documentation Rules

### 1️⃣ Log Everything
Use the command below to record every terminal session:
```bash
script -a logs/install-session.log

## 🖼️ Network Architecture Diagram
              ┌───────────────────────────────────────────┐
              │          Windows Server 2022 (DC01)        │
              │-------------------------------------------│
              │ Roles: AD DS, DNS, DHCP                   │
              │ Domain: itnexttech.com                     │
              │ IP: 192.168.0.110                          │
              └───────────────────────────────────────────┘
                               │
                               │
                    DNS + Authentication
                              │
                               ▼
      ┌──────────────────────────────────────────────┐
      │             Rocky Linux 9.6 (rocky01)        │
      │----------------------------------------------│
      │ Hostname: rocky01.itnexttech.com             │
      │ IP: 192.168.0.100                       │
      │ Services: cPanel, WHM, Exim, Dovecot, SSSD   │
      │ Integrated with AD (realm join)              │
      │ Auth: Domain Users via itnexttech.com        │
      └──────────────────────────────────────────────┘
                               │
                               │
                Web Hosting + Email Management
                               │
                               ▼
    ┌─────────────────────────────────────────────┐
    │                 End Users / Clients          │
    │---------------------------------------------│
    │ Access via:                                 │
    │  - WHM / cPanel Web Interface                │
    │  - Roundcube Webmail                         │
    │  - SSH (AD-authenticated)                    │
    └─────────────────────────────────────────────┘


