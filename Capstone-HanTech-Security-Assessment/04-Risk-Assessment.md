# Vulnerability Risk Assessment – HanTech

## 1. Introduction

Following the OpenVAS vulnerability assessment, a risk assessment was conducted on the five selected findings to understand their potential impact on HanTech's systems and business operations.

The purpose was to move beyond technical vulnerability identification and evaluate how each weakness could expose the organisation to security incidents.

The assessment considered two main factors:

- **Likelihood:** How likely the vulnerability could be exploited if the affected service were accessible to an attacker.
- **Impact:** The potential consequences for confidentiality, integrity, availability, and business operations.

The ratings represent an analyst assessment based on the available laboratory evidence and assumed organisational exposure. They are not confirmed measurements of risk in a live HanTech production environment.

## 2. Risk Rating Methodology

### Likelihood

| Rating | Meaning |
|---|---|
| Low | Exploitation is unlikely under the assumed conditions. |
| Medium | Exploitation is possible but may require specific conditions. |
| High | Exploitation is reasonably likely if the vulnerable service is accessible. |

### Impact

| Rating | Meaning |
|---|---|
| Low | Limited effect on systems or operations. |
| Medium | Noticeable disruption or limited information exposure. |
| High | Significant compromise of systems, data, or operations. |
| Critical | Potential for severe unauthorised access, major data compromise, or serious operational disruption. |

### Overall Risk

The overall risk rating considers both likelihood and impact, alongside the nature of the weakness.

For this project, the five selected findings were assigned Critical overall risk because of their severe authentication or remote-access weaknesses and potential consequences.

## 3. Vulnerability Risk Assessment Matrix

| Vulnerability | Likelihood | Impact | Overall Risk |
|---|---|---|---|
| MySQL root account with empty password | High | Critical | Critical |
| vsftpd 2.3.4 backdoor-related vulnerability | High | Critical | Critical |
| Passwordless rlogin root access | High | Critical | Critical |
| DistCC remote code execution | High | High | Critical |
| Apache Tomcat Manager default credentials | High | Critical | Critical |

## 4. Explanation of Individual Risk Ratings

### 4.1 MySQL Root Account with Empty Password

**Likelihood: High**

The scan reported successful authentication using the MySQL root account without a password. If the database service is reachable by an attacker, this weakness could make unauthorised access considerably easier.

**Impact: Critical**

The root account has extensive database privileges. Unauthorised access could result in sensitive information being exposed, altered, or deleted.

**Overall Risk: Critical**

The combination of weak authentication and potentially extensive database privileges makes this a serious security concern.

### 4.2 vsftpd 2.3.4 Backdoor-Related Vulnerability

**Likelihood: High**

The scanner identified a finding associated with the known vsftpd backdoor. The risk is significant if the affected compromised package is present and the relevant service is accessible.

**Impact: Critical**

Successful exploitation could provide unauthorised command execution and create an opportunity for further system compromise.

**Overall Risk: Critical**

The potential for unauthorised access and command execution justifies prioritising investigation and remediation. The exact package provenance should be validated before concluding that the historical backdoor is present.

### 4.3 Passwordless rlogin Root Access

**Likelihood: High**

The scan reported passwordless root access through rlogin. If the service is reachable by an unauthorised user, the lack of authentication creates a serious exposure.

**Impact: Critical**

Root-level access could allow an attacker to modify system configurations, access files, disrupt services, or compromise system security.

**Overall Risk: Critical**

The possibility of unauthorised privileged access makes this one of the most serious findings.

### 4.4 DistCC Remote Code Execution

**Likelihood: High**

OpenVAS reported remote command execution through DistCC. The scan evidence showed execution under the daemon account.

**Impact: High**

Although the observed command execution was not under root privileges, an attacker could still misuse the service account to access available resources or attempt further compromise.

**Overall Risk: Critical**

The remote execution capability represents a serious exposure, even though the observed execution was under a limited service account rather than root.

### 4.5 Apache Tomcat Manager Default Credentials

**Likelihood: High**

OpenVAS reported successful authentication using default Tomcat credentials. If the management interfaces are accessible to unauthorised users, the weakness could be exploited.

**Impact: Critical**

Unauthorised access to application management functions could allow interference with application administration and potentially application deployment or modification, depending on permissions.

**Overall Risk: Critical**

Default credentials on management interfaces create a significant risk of unauthorised administrative access.

## 5. Risk Prioritisation

Based on the assessment, all five findings require prompt attention.

The recommended priority is:

1. **MySQL root account with empty password:** Secure privileged database authentication and restrict access.
2. **Passwordless rlogin root access:** Disable insecure remote administration and replace it with SSH.
3. **Tomcat Manager default credentials:** Replace default credentials and restrict management access.
4. **vsftpd backdoor-related finding:** Verify package integrity and replace any affected installation.
5. **DistCC remote code execution:** Disable or patch the service and restrict network access.

These priorities are proposed remediation priorities, not a claim that the findings have already been fixed.

## 6. Business Implications

If similar weaknesses existed in HanTech's production environment, they could expose the organisation to:

- Unauthorised access to business systems.
- Exposure or manipulation of sensitive information.
- Disruption of business applications and services.
- Loss of customer and stakeholder confidence.
- Financial and reputational damage.
- Potential regulatory and contractual consequences, depending on the data and services affected.

## 7. Limitations and Assumptions

The risk ratings are based on the findings from a controlled Metasploitable 2 laboratory assessment.

The actual risk to a production organisation would require further information, including:

- Business value and criticality of affected assets.
- Network exposure and accessibility of services.
- Sensitivity of information stored or processed.
- Existing security controls.
- Threat environment and likelihood of exploitation.
- Applicable legal, regulatory, and contractual obligations.

CVSS scores were used to understand technical severity but were not treated as direct business risk ratings.

## 8. Conclusion

The risk assessment helped prioritise the five selected vulnerabilities according to their potential consequences.

It demonstrated that vulnerability management should not stop at identifying weaknesses. Security teams must understand the likelihood of exploitation, the potential business impact, and the actions required to reduce exposure.

The results provide the foundation for the next stage of the project: recommending security controls to address the identified risks.
