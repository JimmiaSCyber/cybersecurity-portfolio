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

## Step-by-Step Configuration and Validation Process

### Step 1: Access the Windows Desktop

![Home Screen Display](screenshots/windows-home-screen.png)

The system is booted into a Windows 11 environment.  
This represents a typical client workstation in a real-world MSP environment.

---

## Step 2: Open the Start Menu

![Click the start button](screenshots/click-start-button.png)

The Start button is selected from the taskbar.

This is the standard method for accessing system applications and administrative tools.

---

## Step 3: Search for Windows Security

![Type windows security ](screenshots/type-windows-security.png)

"Windows Security" is typed into the search bar.

Using search allows quick access to security tools without navigating through Control Panel or Settings menus — a common time-saving practice in IT support environments.

---

## Step 4: Open Virus & Threat Protection

![Open Virus & Threat Protection ](screenshots/click-virus-threat-protection.png)

Inside Windows Security, **Virus & Threat Protection** is selected.

This section controls Microsoft Defender Antivirus and handles:

- Malware detection
- Threat scanning
- Real-time protection
- Scan history

In MSP environments, this is one of the first places technicians check when investigating suspected malware.

---

## Step 5: Run a Quick Scan

![Run a Quick Scan ](screenshots/click-quick-scan.png)

The **Quick Scan** option is selected.

A quick scan checks common infection locations such as:

- Running processes
- System memory
- Startup locations
- Critical system folders

Real-World Importance:
Quick scans are often performed during routine maintenance or when a client reports unusual system behavior.

---

## Step 6: Monitor Scan Progress

![Wait for scan to complete](screenshots/wait-for-scan-to-complete.png)

The scan runs and displays:

- Files scanned
- Estimated time remaining

This confirms that antivirus definitions are functioning properly and that the engine is actively scanning.

In real-world support, verifying scan execution ensures that endpoint protection has not been disabled or corrupted.

---

## Step 7: Access Virus & Threat Protection Settings

![Manage Settings](screenshots/manage-settings.png)

"Manage settings" is selected under Virus & Threat Protection settings.

This is where core Defender protections are configured.

---

## Step 8: Verify Real-Time Protection

![Real time protection enable](screenshots/real-time-protection.png)

Real-Time Protection is confirmed as **ON**.

Real-Time Protection is critical because:

- It actively monitors file activity.
- It blocks malicious programs before execution.
- It prevents zero-day threats from running unchecked.

If Real-Time Protection is disabled in a production environment, the endpoint becomes significantly vulnerable.

MSP technicians frequently verify this setting when onboarding new devices or investigating security incidents.

---

## Step 9: Navigate Back to Main Threat Page

![Navigate back to main page](screenshots/click-the-back-button.png)

The back arrow is selected to return to the main Virus & Threat Protection dashboard.

This ensures proper navigation and confirms no configuration errors occurred.

---

## Step 10: Open Scan Options

![Open Scan Options](screenshots/scan-options.png)

"Scan options" is selected.

This allows selection of:

- Quick Scan
- Full Scan
- Custom Scan
- Microsoft Defender Offline Scan

---

## Step 11: Perform a Full Scan

![Perform full scan](screenshots/full-scan.png)

The **Full Scan** option is selected.

A full scan checks:

- All files
- All running programs
- Entire hard drive contents

Real-World Importance:
Full scans are used when:

- Persistent malware is suspected
- A quick scan returns suspicious behavior
- A system shows performance degradation
- A machine is being prepared for production use

---


















