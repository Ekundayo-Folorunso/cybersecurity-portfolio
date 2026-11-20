# Executive Summary – HanTech Cybersecurity Assessment

## 1. Project Overview

As part of the HanTech cybersecurity capstone project, our team conducted a security assessment to identify potential vulnerabilities, evaluate their associated risks, and recommend practical measures to improve the organisation's security posture.

HanTech was presented as a medium-sized technology company operating business applications, legacy systems, and cloud-based services.

The project focused on understanding how technical security weaknesses could affect business operations, sensitive information, and organisational reputation.

The assessment combined a practical vulnerability scanning exercise with risk analysis, security control recommendations, governance policies, and a conceptual cloud security assessment.

## 2. Key Findings

Using Greenbone OpenVAS, we assessed a Metasploitable 2 virtual machine in a controlled laboratory environment.

The scan initially identified 716 findings. After applying a minimum Quality of Detection (QoD) threshold of 70%, 62 findings were displayed for review.

Five significant findings were selected for detailed analysis:

1. **MySQL root account with an empty password:** A weak authentication configuration that could expose database information to unauthorised access.
2. **vsftpd 2.3.4 backdoor-related vulnerability:** A finding associated with compromised software packages that could permit unauthorised command execution if the affected package is present.
3. **Passwordless rlogin root access:** An insecure remote access configuration that could expose privileged system access.
4. **DistCC remote code execution:** A weakness that could allow unauthorised remote command execution under the service account.
5. **Apache Tomcat Manager default credentials:** Default login credentials that could expose application management interfaces to unauthorised users.

All five selected findings had scanner-reported CVSS scores within the Critical severity range.

These findings demonstrate how weak authentication, insecure remote services, and vulnerable software configurations can increase an organisation's exposure to cyber threats.

## 3. Highest-Risk Areas

The assessment identified three particularly important areas requiring attention:

- **Privileged access weaknesses:** The MySQL and rlogin findings demonstrated the potential consequences of inadequate authentication and privileged account protection.
- **Insecure software and remote services:** The vsftpd and DistCC findings highlighted the importance of trusted software, secure configuration, patching, and network restrictions.
- **Exposed application management interfaces:** The Tomcat finding demonstrated the risks associated with retaining default credentials and insufficient access restrictions.

The team assessed the five selected findings as Critical overall risk based on the available technical evidence and assumed exposure conditions.

The actual business risk would require validation against HanTech's production assets, network exposure, data sensitivity, and existing controls.

## 4. Recommended Security Controls

To reduce the identified risks, the following measures were recommended:

- Enforce strong passwords and multi-factor authentication for sensitive access.
- Disable insecure remote administration services such as rlogin.
- Replace default application and database credentials.
- Apply least-privilege access management.
- Remove or update vulnerable and untrusted software.
- Restrict unnecessary network ports and exposed services.
- Monitor privileged account activity and suspicious network connections.
- Conduct regular vulnerability assessments and verify remediation.

These controls would help reduce the likelihood of unauthorised access, data compromise, and service disruption.

## 5. Recommended Governance Policies

The team also recommended organisational policies to ensure that security improvements are consistently maintained.

The proposed policies include:

- Access Control Policy.
- Password and Authentication Policy.
- Patch and Software Lifecycle Management Policy.
- Vulnerability Management Policy.
- Remote Access and Network Security Policy.
- Logging and Security Monitoring Policy.

These policies establish responsibilities, define acceptable security practices, and provide a framework for monitoring compliance.

## 6. Cloud Security Considerations

The project also considered potential security risks associated with HanTech's cloud environment.

Key areas included cloud misconfiguration, weak credentials, excessive permissions, unencrypted data, insecure APIs, insider threats, and distributed denial-of-service attacks.

Recommendations included implementing Identity and Access Management (IAM), enforcing multi-factor authentication, applying least privilege, encrypting sensitive information, enabling cloud audit logging, and understanding the shared responsibility model.

This section was a conceptual assessment rather than an independent technical scan of live cloud infrastructure.

## 7. Overall Security Assessment

The project demonstrated that serious security weaknesses can arise from poor authentication practices, insecure configurations, outdated or compromised software, and insufficient access management.

Although the practical vulnerability assessment was performed against a deliberately vulnerable laboratory machine rather than HanTech's actual production environment, the findings provided a useful basis for understanding how similar weaknesses could affect a business.

The combination of vulnerability identification, risk assessment, technical recommendations, governance policies, and cloud security considerations provides a structured approach to improving organisational security.

## 8. Final Recommendation

HanTech should adopt a proactive, risk-based cybersecurity approach.

Management should prioritise the validation and remediation of critical security weaknesses, establish clear security responsibilities, enforce appropriate policies, and maintain continuous vulnerability management and security monitoring.

Cybersecurity should be treated as an ongoing business responsibility rather than a one-time technical exercise.

By combining effective technical controls with governance, risk management, employee awareness, and regular security reviews, HanTech can strengthen its resilience and better protect its systems, information, customers, and business operations.

---

**Project:** From Vulnerability to Compliance: Securing Legacy and Cloud Systems at HanTech.

**Assessment tools:** Greenbone OpenVAS and Metasploitable 2 laboratory environment.

**Assessment approach:** Practical vulnerability assessment, risk analysis, security control recommendations, GRC policy development, and conceptual cloud security assessment.
