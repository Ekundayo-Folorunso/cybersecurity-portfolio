# GRC Policy Recommendations – HanTech

## 1. Introduction

Following the vulnerability assessment and recommended security controls, this section outlines the Governance, Risk and Compliance (GRC) policies recommended for HanTech.

The purpose of these policies is to establish clear security requirements, assign responsibilities, promote accountability, and ensure that security controls are consistently applied across the organisation.

The policies are designed to address the weaknesses identified during the assessment while supporting a stronger security culture.

## 2. Recommended GRC Policies

### 2.1 Access Control Policy

**Purpose**

To ensure that employees, contractors, and third parties only access systems and information required for their authorised responsibilities.

**Policy requirements**

- Every user must have a unique account.
- Access permissions must be based on job responsibilities.
- The principle of least privilege must be applied.
- Administrative accounts must be restricted to authorised personnel.
- Access rights must be reviewed periodically.
- User access must be revoked promptly when employment or business responsibilities end.

**Risks addressed**

- Unauthorised access to databases and business applications.
- Excessive user privileges.
- Misuse of administrative accounts.
- Unauthorised modification or disclosure of information.

**Relevant project findings:** MySQL root account, rlogin root access, and Tomcat Manager default credentials.

**Policy owner:** IT Manager, supported by the Information Security Team.

### 2.2 Password and Authentication Policy

**Purpose**

To establish minimum authentication requirements that protect organisational systems and user accounts from unauthorised access.

**Policy requirements**

- Default passwords must be changed before systems are placed into service.
- Passwords must be unique and sufficiently strong.
- Shared accounts and password sharing must be prohibited unless formally approved and controlled.
- Multi-factor authentication must be implemented for privileged and other high-risk access where supported.
- Authentication failures and suspicious login attempts must be monitored.
- Compromised credentials must be changed promptly.

**Risks addressed**

- Weak or missing passwords.
- Default credentials.
- Unauthorised account access.
- Credential-based attacks.

**Relevant project findings:** MySQL empty root password and Tomcat default credentials.

**Policy owner:** Information Security Team and IT Manager.

### 2.3 Patch and Software Lifecycle Management Policy

**Purpose**

To ensure that operating systems, applications, and supporting services remain supported, updated, and protected against known security weaknesses.

**Policy requirements**

- Maintain an inventory of approved software and systems.
- Obtain software from trusted and verified sources.
- Assess security updates and vendor advisories.
- Prioritise critical vulnerabilities for timely remediation.
- Remove unsupported or unnecessary software.
- Test updates appropriately before deployment.
- Maintain records of patching and remediation activities.

**Risks addressed**

- Exploitation of known software vulnerabilities.
- Installation of compromised packages.
- Use of outdated or unsupported software.
- Unnecessary exposure through vulnerable services.

**Relevant project findings:** vsftpd backdoor-related vulnerability and DistCC remote code execution.

**Policy owner:** IT Operations and Information Security Team.

### 2.4 Vulnerability Management Policy

**Purpose**

To establish a consistent process for identifying, evaluating, prioritising, remediating, and verifying security vulnerabilities.

**Policy requirements**

- Conduct vulnerability assessments at defined intervals.
- Maintain an inventory of organisational assets.
- Review and validate scanner findings.
- Prioritise remediation using technical severity, exploitability, asset criticality, and business impact.
- Assign remediation responsibilities and target dates.
- Perform follow-up scans or tests to verify corrective actions.
- Document accepted risks and obtain appropriate management approval.

**Risks addressed**

- Unidentified security weaknesses.
- Delayed vulnerability remediation.
- Unmanaged exposure of critical systems.
- Lack of accountability for security findings.

**Relevant project findings:** All five selected OpenVAS vulnerabilities.

**Policy owner:** Information Security Manager or designated Security Lead.

### 2.5 Remote Access and Network Security Policy

**Purpose**

To ensure that remote connections and network services are securely configured and accessible only to authorised users and systems.

**Policy requirements**

- Insecure remote administration services must be disabled.
- Approved encrypted remote access methods must be used.
- Network access must be restricted according to business requirements.
- Firewalls must block unnecessary ports and services.
- Administrative access must be limited to approved management networks.
- Externally accessible services must undergo security review.
- Unusual network activity must be investigated.

**Risks addressed**

- Unauthorised remote access.
- Exposure of vulnerable network services.
- Remote command execution.
- Unnecessary network attack surfaces.

**Relevant project findings:** rlogin, vsftpd, and DistCC.

**Policy owner:** Network Administrator and Information Security Team.

### 2.6 Logging and Security Monitoring Policy

**Purpose**

To ensure that security-relevant activities are recorded, monitored, and investigated to support early detection and incident response.

**Policy requirements**

- Enable logging on critical systems and applications.
- Record authentication and privileged account activities.
- Protect logs against unauthorised modification or deletion.
- Review alerts and suspicious events.
- Define log retention requirements according to business, legal, and regulatory obligations.
- Establish an escalation process for suspected security incidents.
- Document investigation and response activities.

**Risks addressed**

- Undetected unauthorised access.
- Privileged account misuse.
- Delayed detection of attacks.
- Inadequate investigation evidence.

**Relevant project findings:** All five vulnerabilities, particularly remote access and administrative interface weaknesses.

**Policy owner:** Information Security Team and IT Operations.

## 3. Policy Implementation and Accountability

For the policies to be effective, HanTech should assign clear responsibilities.

| Role | Responsibility |
|---|---|
| Board / Senior Management | Approve security policies and provide oversight |
| CEO | Support implementation and organisational accountability |
| IT Manager | Coordinate technical implementation |
| Information Security Team | Monitor compliance and review security risks |
| System Administrators | Implement system-level security requirements |
| Employees and Contractors | Follow approved policies and report security concerns |

These roles represent a proposed governance structure for the simulated HanTech organisation.

## 4. Policy Review and Compliance Monitoring

HanTech should establish a process for reviewing and monitoring policy implementation.

Recommended activities include:

- Review policies at least annually and whenever significant changes occur.
- Conduct periodic access reviews.
- Review vulnerability assessment results and remediation records.
- Monitor security logs and investigate unusual activity.
- Provide security awareness training.
- Maintain evidence of policy approval and implementation.
- Report significant security risks and unresolved issues to management.

Policy exceptions should be documented, justified, approved by an appropriate authority, and reviewed periodically.

## 5. Relationship Between Policies and Technical Controls

The recommended policies provide organisational direction for the technical controls proposed in the previous stage.

| Policy | Supporting Technical Controls |
|---|---|
| Access Control Policy | Least privilege, role-based access, account reviews |
| Password and Authentication Policy | Strong passwords, MFA, removal of default credentials |
| Patch and Software Lifecycle Management Policy | Software updates, trusted packages, removal of unsupported software |
| Vulnerability Management Policy | OpenVAS assessments, risk prioritisation, remediation verification |
| Remote Access and Network Security Policy | SSH, firewall restrictions, secure network configuration |
| Logging and Security Monitoring Policy | Centralised logs, alert monitoring, incident investigation |

## 6. Conclusion

The recommended GRC policies provide a framework for ensuring that security improvements are not treated as one-time technical fixes.

By establishing clear rules, assigning responsibilities, and monitoring compliance, HanTech can create a more consistent approach to managing cybersecurity risks.

This stage demonstrates the connection between technical vulnerability management and organisational governance: security tools help identify weaknesses, technical controls help address them, and policies ensure that security practices are maintained over time.
