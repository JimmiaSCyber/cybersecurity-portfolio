# Windows Security Controls Lab

## Objective

This lab focuses on configuring and understanding built-in Windows security controls relevant to IT support and MSP environments.

The goal is to demonstrate hands-on experience managing endpoint security settings, user controls, and system protection mechanisms.

---

## Topics Covered

- Windows Defender Antivirus Configuration
- Windows Firewall with Advanced Security
- Local User Account Management
- User Account Control (UAC)
- Encrypting File System (EFS)
- NTFS Permissions
- Local Security Policy
- Command Line Security Tools

---

## Lab Environment

- Windows 10 / 11 (Virtual Machine)
- Local Administrator Access

---

## Relevance to IT / MSP Roles

This lab demonstrates practical endpoint administration and system hardening skills that are essential for:

- Help Desk Support
- MSP Technician Roles
- Junior System Administration
- Endpoint Security Management

Each section below documents the configuration process, screenshots, and analysis of security impact.

# Task 1 – Configure Windows Defender Antivirus Settings

## Objective

Review and configure Windows Defender Antivirus settings to ensure real-time protection and threat mitigation are properly enabled on a Windows workstation.

---

## Steps Performed

1. Opened **Windows Security** from the Start menu.
2. Navigated to **Virus & Threat Protection**.
3. Reviewed current protection status.
4. Verified that:
   - Real-time protection is enabled
   - Cloud-delivered protection is enabled
   - Automatic sample submission is enabled
5. Opened **Virus & Threat Protection Settings** to confirm configuration.

---

## Security Features Reviewed

### Real-Time Protection
Monitors files and programs for malicious activity as they are accessed.

### Cloud-Delivered Protection
Uses Microsoft’s cloud intelligence to detect emerging threats.

### Automatic Sample Submission
Sends suspicious files to Microsoft for deeper analysis.

---

## Why This Matters

Windows Defender is the first line of defense against malware on endpoint systems.

Ensuring these protections are enabled:

- Reduces malware infection risk
- Prevents unauthorized software execution
- Strengthens baseline endpoint security
- Supports compliance with security best practices

In MSP environments, verifying endpoint antivirus configuration is a common support task.























