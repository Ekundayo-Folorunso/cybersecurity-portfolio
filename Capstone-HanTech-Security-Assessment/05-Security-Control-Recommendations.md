# Security Control Recommendations – HanTech

## 1. Introduction

Following the vulnerability assessment and risk analysis, security controls were recommended to address the five critical vulnerabilities identified during the HanTech capstone project.

The objective is not simply to fix individual technical weaknesses but to establish preventive, detective, and corrective measures that improve the organisation's overall security posture.

The recommendations consider access control, authentication, secure configuration, patch management, network security, and continuous monitoring.

## 2. Recommended Security Controls

### 2.1 MySQL Root Account with Empty Password

**Identified risk:** Unauthorised users could gain privileged database access because the MySQL root account accepts an empty password.

**Recommended controls:**

1. Enforce a strong, unique password for the MySQL root account.
2. Disable remote root login unless there is a justified operational requirement.
3. Apply the principle of least privilege to database accounts.
4. Restrict TCP port 3306 to authorised application servers and administrators.
5. Enable database authentication and access logging.

**How these controls reduce risk**

Strong authentication makes unauthorised login more difficult. Restricting remote root access reduces the number of systems that can attempt privileged authentication. Least privilege limits the damage that could result from compromised accounts.

**Responsible team:** Database Administrator and IT Security Team.

**Verification:** Confirm that empty-password authentication fails, remote root access is restricted, and database users have only the permissions required for their duties.

### 2.2 vsftpd 2.3.4 Backdoor-Related Vulnerability

**Identified risk:** An affected compromised vsftpd package could expose the system to unauthorised command execution.

**Recommended controls:**

1. Verify the installed package's origin and integrity.
2. Remove any confirmed affected package and reinstall software from a trusted source.
3. Replace unencrypted FTP with SFTP or another approved secure file-transfer solution.
4. Restrict access to file-transfer services through firewall rules.
5. Monitor unusual connections and activity involving TCP ports 21 and 6200.
6. Establish a software patch and update management process.

**How these controls reduce risk**

Using trusted software reduces the possibility of installing compromised packages. Secure file transfer protects data in transit, while network restrictions reduce exposure to unauthorised connections. Monitoring helps identify suspicious activity.

**Responsible team:** System Administrator and IT Security Team.

**Verification:** Confirm package integrity, verify that affected software has been removed, test secure file transfer, and review firewall and monitoring configurations.

### 2.3 Passwordless rlogin Root Access

**Identified risk:** The rlogin service allows root access without password authentication.

**Recommended controls:**

1. Disable the rlogin service.
2. Replace insecure remote administration with SSH.
3. Require strong authentication for administrative access.
4. Introduce multi-factor authentication where supported.
5. Restrict administrative connections to approved management networks.
6. Monitor privileged login attempts and remote administrative activity.

**How these controls reduce risk**

Disabling rlogin removes the insecure access method. SSH provides encrypted remote administration, while stronger authentication and network restrictions reduce the opportunity for unauthorised privileged access.

**Responsible team:** System Administrator and IT Security Team.

**Verification:** Confirm that rlogin is disabled, unauthorised connections to TCP port 513 are blocked, and administrative access is performed through approved SSH configurations.

### 2.4 DistCC Remote Code Execution

**Identified risk:** An attacker may execute commands remotely through the vulnerable DistCC service.

**Recommended controls:**

1. Disable DistCC if it is not required.
2. Upgrade or patch affected software.
3. Restrict TCP port 3632 to trusted systems where the service is operationally necessary.
4. Apply least privilege to the service account.
5. Monitor unusual process execution and network connections.
6. Include the service in routine vulnerability assessments.

**How these controls reduce risk**

Disabling unnecessary services removes an attack surface. Patching addresses known weaknesses, while firewall restrictions prevent unauthorised systems from reaching the service. Least privilege limits the potential impact if the service is compromised.

**Responsible team:** System Administrator and IT Security Team.

**Verification:** Confirm that unnecessary DistCC services are disabled, the software is updated where required, and access to TCP port 3632 is restricted.

### 2.5 Apache Tomcat Manager Default Credentials

**Identified risk:** Default credentials provide unauthorised users with access to Tomcat management interfaces.

**Recommended controls:**

1. Replace default credentials immediately.
2. Enforce strong and unique administrator passwords.
3. Restrict access to the Manager and Host Manager interfaces.
4. Apply role-based access control to administrative accounts.
5. Introduce multi-factor authentication through a supported identity solution where appropriate.
6. Review administrative accounts and authentication logs regularly.

**How these controls reduce risk**

Removing default credentials prevents access using commonly known login combinations. Restricting management interfaces reduces exposure, while role-based access control ensures administrators receive only the permissions necessary for their responsibilities.

**Responsible team:** Application Administrator and IT Security Team.

**Verification:** Confirm that default credentials no longer work, unauthorised users cannot reach management interfaces, and administrative permissions are appropriately restricted.

## 3. Summary of Recommended Controls

| Vulnerability | Primary Control | Expected Security Benefit |
|---|---|---|
| MySQL empty root password | Strong authentication and least privilege | Prevents unauthorised privileged database access |
| vsftpd backdoor | Trusted software and secure file transfer | Reduces exposure to compromised software |
| Passwordless rlogin | Disable rlogin and use SSH | Removes insecure remote administration |
| DistCC remote code execution | Patch, disable if unnecessary, and restrict access | Reduces remote command execution exposure |
| Tomcat default credentials | Replace defaults and restrict management access | Prevents unauthorised application administration |

## 4. Additional Organisation-Wide Security Controls

In addition to the individual recommendations, HanTech should implement organisation-wide controls.

### Access Control and Identity Management

- Establish unique user accounts.
- Apply role-based access control.
- Review user permissions regularly.
- Remove access when employees leave or change roles.
- Enforce least privilege for administrative accounts.

### Patch and Vulnerability Management

- Maintain an inventory of hardware and software assets.
- Perform regular vulnerability assessments.
- Prioritise remediation according to risk.
- Establish patching timelines for critical and high-risk vulnerabilities.
- Verify remediation through follow-up scans and testing.

### Security Monitoring and Logging

- Centralise security logs where practical.
- Monitor authentication failures and unusual login activity.
- Monitor privileged account activity.
- Investigate suspicious network connections.
- Establish an incident reporting and escalation process.

### Backup and Recovery

- Maintain regular backups of critical information.
- Protect backup systems from unauthorised access.
- Test restoration procedures.
- Establish recovery objectives for important business services.

## 5. Remediation Priorities

The following implementation sequence is recommended:

**Priority 1 – Immediate actions**
- Remove the MySQL empty password.
- Disable passwordless rlogin.
- Replace Tomcat default credentials.
- Investigate and verify the vsftpd package.

**Priority 2 – Short-term actions**
- Patch or disable vulnerable DistCC services.
- Restrict unnecessary network access.
- Review administrative accounts and permissions.
- Strengthen authentication requirements.

**Priority 3 – Ongoing improvements**
- Conduct regular vulnerability assessments.
- Review security policies and access rights.
- Monitor security logs.
- Test backups and incident response procedures.
- Track remediation activities to completion.

These priorities are recommendations based on the laboratory findings and should be adjusted following validation against actual production asset exposure and business requirements.

## 6. Conclusion

The recommended controls provide practical steps for addressing the weaknesses identified during the HanTech vulnerability assessment.

The exercise demonstrates that effective cybersecurity requires more than identifying vulnerabilities. Organisations must implement appropriate controls, assign responsibilities, verify that corrective actions work, and continuously monitor their systems.

By combining technical controls with sound security management practices, HanTech can reduce its exposure to unauthorised access, data compromise, and service disruption.
