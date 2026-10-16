# Enterprise Active Directory Lab: Automated Drive Mapping, RBAC Data Segmentation, and Object Auditing

## 1. Project Overview
This project simulates an enterprise-level identity management, storage segmentation, and security auditing architecture within a virtualized sandbox. Using Windows Server as an Active Directory Domain Controller and a Windows 11 Enterprise client, this build automates user storage provisioning via PowerShell and Group Policy, enforces data privacy through Access-Based Enumeration (ABE), and implements centralized compliance auditing via Windows Security Event logging.

---

## 2. Architecture & Topology
* **Domain Controller:** Windows Server (`lab.local`, `192.168.10.10`)
  * Core Services: Active Directory Domain Services (AD DS), DNS, File and Storage Services
  * Roles Configured: SMB File Server, Central Group Policy Management
* **Client Endpoint:** Windows 11 Enterprise (Domain-Joined)
* **Virtualization Layer:** Oracle VirtualBox running on an internal virtual network bridge
* **Central File Share:** `\\lab.local\CompanyShare` (Local Server Path: `C:\CompanyShare`)

---

## 3. Directory Structure & Identity Management
An Organizational Unit (OU) and Role-Based Access Control (RBAC) hierarchy was established to mirror an enterprise department structure:

```text
lab.local
└── Employees (OU)
    ├── IT-Department (OU)
    │   ├── User: John Smith (jsmith)
    │   └── Security Group: SG-IT-Department
    └── HR Department (OU)
        ├── User: Jane Doe (jdoe)
        └── Security Group: SG-HR-Department
