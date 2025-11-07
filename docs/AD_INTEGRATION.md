# Rocky Linux 9.6 — Active Directory (AD) Integration Documentation

## Project Overview
This project documents the integration of **Rocky Linux 9.6** with a **Windows Active Directory domain** (`itnexttech.com`).  
Integration allows Linux servers to authenticate users against the AD domain, providing **centralized authentication, improved security, and simplified user management**.

---

## Objectives of AD Integration

1. **Centralized Authentication:**  
   Users can log into Linux servers using their AD credentials.  
2. **Simplified Management:**  
   No need to maintain separate Linux accounts; AD groups and users control access.  
3. **Security & Compliance:**  
   Centralized password policies, auditing, and MFA can be applied.  
4. **Single Sign-On (SSO):**  
   Users have a unified login experience across Windows and Linux systems.  
5. **Portfolio / Learning Purpose:**  
   Demonstrates enterprise-level Linux/Windows interoperability and system administration skills.

---

# Stage 1 — Preliminary Checks

### Step 1.1 — Verify Network Connectivity
**Why:** AD integration requires communication with the domain controller (DC) over the network.  

**Command:**
```bash
ping <domain-controller-ip> -c 4
ping itnexttech.com -c 4
