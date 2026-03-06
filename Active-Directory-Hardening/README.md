---

## Task 1 – Authentication & Communication Hardening

In this task, I configured multiple authentication and communication security settings within Active Directory using the **Group Policy Management Editor (GPME)**.

The goal of this configuration was to:

- Prevent weak password hash storage
- Enforce signed network communication
- Reduce exposure to replay and Man-in-the-Middle (MiTM) attacks
- Strengthen password policy enforcement
- Improve identity security posture within the domain

All configurations were performed at the domain policy level to ensure centralized enforcement across domain-joined systems.

---

### Step 1 – Access Group Policy Management Editor (GPME)

To configure domain-level security settings:

Start → Administrative Tools → Group Policy Management  
Navigate to the appropriate domain-level GPO for editing.

Group Policy path used throughout this task:

Computer Configuration  
→ Policies  
→ Windows Settings  
→ Security Settings  

**Technical Insight:**

Group Policy Management Editor allows centralized configuration of security policies that apply to all domain-joined machines. This is critical in enterprise environments where manual local configuration is not scalable.

**Real-World Importance:**

In enterprise environments, security hardening must be enforced centrally. Using GPO ensures consistency, compliance, and prevents configuration drift across hundreds or thousands of systems.

This demonstrates my understanding of centralized security policy management within Active Directory.

---

## LAN Manager (LM) Hash Hardening

### Step 2 – Disable LM Hash Storage

Navigation Path:

Computer Configuration  
→ Policies  
→ Windows Settings  
→ Security Settings  
→ Local Policies  
→ Security Options  
→ "Network security: Do not store LAN Manager hash value on next password change"

I selected:
✔ Define this policy setting  
✔ Enabled

**Technical Insight:**

Windows can generate both:

- LM Hash (weak)
- NT Hash (stronger)

LM hashes are significantly weaker and vulnerable to brute-force attacks due to:

- Uppercase conversion
- 7-character chunking
- Lack of salting
- Faster cracking capability

By disabling LM hash storage, I ensured that only NT hashes are retained for authentication purposes.

**Real-World Importance:**

Attackers often extract password hashes during post-exploitation activities and attempt offline cracking.

If LM hashes are stored, passwords under 15 characters can be cracked rapidly.

Disabling LM hash storage:

- Reduces credential cracking success rates
- Strengthens password protection
- Eliminates legacy authentication weaknesses

This configuration demonstrates my understanding of credential storage security and hash-based attack mitigation within Active Directory.

---

## SMB Signing Configuration

### Step 3 – Enable SMB Signing

Navigation Path:

Computer Configuration  
→ Policies  
→ Windows Settings  
→ Security Settings  
→ Local Policies  
→ Security Options  
→ "Microsoft network server: Digitally sign communications (always)"

I selected:
✔ Enable

**Technical Insight:**

SMB (Server Message Block) is used for:

- File sharing
- Printer access
- Network communication

Without signing, SMB traffic can be intercepted and modified via Man-in-the-Middle (MiTM) attacks.

SMB signing ensures:

- Integrity verification
- Detection of altered packets
- Secure communication between client and server

**Real-World Importance:**

SMB is heavily targeted during:

- Lateral movement
- Relay attacks
- NTLM relay exploitation

Enforcing SMB signing:

- Prevents unauthorized modification of SMB traffic
- Reduces relay attack success
- Strengthens internal network trust boundaries

This shows I understand network-level attack vectors and how to mitigate them through domain policy enforcement.

---

## LDAP Signing Enforcement

### Step 4 – Require LDAP Signing

Navigation Path:

Computer Configuration  
→ Policies  
→ Windows Settings  
→ Security Settings  
→ Local Policies  
→ Security Options  
→ "Domain controller: LDAP server signing requirements"

Dropdown selection:
✔ Require signing

**Technical Insight:**

LDAP is used for:

- Directory queries
- Authentication
- Resource lookups

Unsigned LDAP requests can be intercepted or replayed by attackers.

LDAP signing enforces:

- Signed requests only
- Rejection of plain-text LDAP communications
- Protection against replay and MiTM attacks

**Real-World Importance:**

Many modern AD attacks exploit weak LDAP configurations.

Requiring LDAP signing:

- Reduces exposure to credential relay attacks
- Protects authentication integrity
- Aligns with Microsoft security hardening baselines

This configuration demonstrates my ability to secure identity communication channels at the domain controller level.

---

## Password Rotation Strategies

### Step 5 – Evaluate Password Rotation Approaches

In this task, I reviewed three password rotation strategies:

1. PowerShell Script Automation
2. Multi-Factor Authentication (MFA) Implementation
3. Group Managed Service Accounts (gMSAs)

**Technical Insight:**

Password rotation reduces long-term credential exposure and limits attacker dwell time.

gMSAs automatically rotate service account passwords every 30 days without manual intervention.

**Real-World Importance:**

Service accounts are high-value targets in enterprise environments.

Using gMSAs:

- Prevents password reuse
- Eliminates hardcoded credentials
- Reduces administrative overhead
- Improves service account security

This demonstrates my understanding of identity lifecycle management and secure credential rotation strategies.

---

## Password Policy Hardening

### Step 6 – Configure Domain Password Policy

Navigation Path:

Computer Configuration  
→ Policies  
→ Windows Settings  
→ Security Settings  
→ Account Policies  
→ Password Policy

Configured settings include:

- Enforce password history: 10–15 previous passwords
- Minimum password length: 10–14 characters
- Complexity requirements: Enabled
- Maximum password age: Configured appropriately

**Technical Insight:**

Strong password policies mitigate:

- Brute force attacks
- Dictionary attacks
- Password spraying
- Credential stuffing

Password complexity ensures:

- Mixed character sets
- No username inclusion
- Increased entropy

**Real-World Importance:**

Weak password policies are one of the most common root causes of AD compromise.

Enforcing strong password policies:

- Increases resistance to automated attacks
- Reduces lateral movement success
- Aligns with security compliance standards (NIST, CIS benchmarks)

This configuration demonstrates my understanding of identity-based attack prevention and enterprise password security enforcement.

---

## Task 1 Summary

Through this task, I:

- Disabled legacy LM hash storage
- Enforced SMB packet signing
- Required LDAP signing at the domain controller level
- Evaluated password rotation strategies
- Strengthened domain password policy controls

These configurations reflect real-world Active Directory hardening techniques used to:

- Reduce credential theft risk
- Prevent replay and MiTM attacks
- Strengthen authentication integrity
- Improve enterprise identity security posture

This lab demonstrates my ability to configure, analyze, and harden authentication mechanisms within an Active Directory environment using Group Policy — a core competency in cybersecurity, security administration, and enterprise identity management roles.
