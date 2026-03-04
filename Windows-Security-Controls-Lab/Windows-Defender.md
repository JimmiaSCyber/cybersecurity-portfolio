# Windows Firewall with Advanced Security

## Objective
Create a custom inbound firewall rule to allow TCP traffic on Port 80 (HTTP) using Windows Defender Firewall with Advanced Security.

This lab demonstrates controlled service exposure, port-level access management, and endpoint hardening practices used in enterprise environments.

---

## Environment
- Windows 11 Pro
- Windows Defender Firewall with Advanced Security (wf.msc)
- Local Administrator privileges
- Standalone workstation (non-domain joined)

---

## Step 1 – Access Firewall Settings

Opened the Start menu and launched the advanced firewall console using:

wf.msc

This opens the Microsoft Management Console (MMC) for Windows Defender Firewall with Advanced Security.

Technical Insight:
This interface allows granular rule creation beyond the basic Windows Security GUI. It supports port-based rules, program-based rules, IP restrictions, and profile-specific enforcement.

Real-World Application:
In enterprise environments, administrators use this console (or Group Policy equivalents) to:
- Harden endpoints
- Restrict unnecessary inbound services
- Enforce security baselines
- Troubleshoot blocked application traffic
- Reduce attack surface

Understanding how to access and navigate this console is foundational for IT support, system administration, and security roles.

---

## Step 2 – Review Inbound Rules

Selected **Inbound Rules** from the left panel.

Inbound rules control traffic coming *into* the system from external hosts.

Technical Insight:
Inbound filtering is critical because external connections represent potential attack vectors. Services listening on open ports can be scanned, fingerprinted, or exploited if misconfigured.

Real-World Application:
In a corporate environment:
- Servers may need specific inbound ports open (web servers, RDP, database servers).
- Workstations typically require minimal inbound exposure.
- Security teams regularly audit inbound rules to ensure no unnecessary services are exposed.

Reviewing rules before creating new ones prevents duplicate or overly permissive configurations.

---

## Step 3 – Create Custom Inbound Rule

Clicked **New Rule** and selected **Port** as the rule type.

Technical Insight:
Port-based rules allow filtering based on TCP or UDP ports rather than application executables. This is useful when:
- Configuring services that rely on known standard ports
- Controlling infrastructure-level access
- Restricting protocol-level communication

Real-World Application:
Security teams often restrict traffic strictly by required ports. For example:
- Port 80 (HTTP)
- Port 443 (HTTPS)
- Port 3389 (RDP)
- Port 22 (SSH)

Using port-level filtering is a fundamental network security control.

---

## Step 4 – Configure Port Rule

Selected:
- Protocol: TCP
- Specific local ports: 80

Port 80 is used for HTTP traffic.

Technical Insight:
TCP is connection-oriented and used for reliable data transmission. HTTP uses TCP because reliability is required for web traffic.

By specifying “Specific local ports,” the rule only applies to traffic targeting port 80, rather than opening all inbound traffic.

Real-World Application:
Opening only required ports:
- Reduces exposure to port scanning
- Limits attack surface
- Follows least privilege principles

If a system is running a local web server (IIS, Apache, internal app), port 80 must be allowed for users to access it.

However, exposing port 80 without business need increases risk.

---

## Step 5 – Assign Action

Selected **Allow the connection**.

Technical Insight:
This setting permits all inbound connections that match the defined criteria (TCP port 80).

Alternative options include:
- Allow the connection if secure (IPSec enforced)
- Block the connection

Real-World Application:
Administrators must intentionally allow required services while blocking unnecessary ones.

Poor firewall configuration can result in:
- Service outages (overly restrictive)
- Security breaches (overly permissive)

Balancing usability and security is a core responsibility in IT operations.

---

## Step 6 – Assign Profile

Selected:
- Domain
- Private
- Public

Technical Insight:
Windows uses network location awareness to determine which firewall profile applies:
- Domain: Connected to corporate Active Directory domain
- Private: Trusted internal networks
- Public: Untrusted networks (coffee shops, airports)

Each profile can enforce different firewall behavior.

Real-World Application:
In enterprise security:
- Domain profile rules are typically more controlled and managed via Group Policy.
- Public profile should be most restrictive.
- Allowing HTTP on Public profile could expose a laptop on open Wi-Fi.

Security-conscious configurations often limit rules to Domain or Private only.

Profile selection is critical for reducing risk in mobile workforce environments.

---

## Step 7 – Name the Rule

Named the rule:

Allow HTTP

Technical Insight:
Clear naming conventions are essential for auditability and future troubleshooting.

Real-World Application:
In enterprise environments, firewall rules may be audited by:
- Security teams
- Compliance auditors
- Incident response teams

Descriptive naming allows quick identification of purpose and reduces configuration confusion.

Example enterprise naming format:
ALLOW_HTTP_TCP80_DOMAIN

---

## Step 8 – Validate Rule Creation

Confirmed the rule appears under Inbound Rules and is enabled.

Technical Insight:
Validation ensures:
- Rule is active
- Profile assignment is correct
- No configuration errors occurred

Real-World Application:
In production environments, administrators must validate firewall changes before closing tickets or deploying systems.

Failure to verify changes can lead to:
- Service outages
- Escalations
- Security gaps

