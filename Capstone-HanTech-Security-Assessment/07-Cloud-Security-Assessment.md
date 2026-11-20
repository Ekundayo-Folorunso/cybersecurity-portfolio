# Cloud Security Assessment – HanTech

## 1. Introduction

As part of the HanTech cybersecurity capstone project, a conceptual cloud security assessment was conducted to identify potential risks associated with hosting business applications, customer information, and organisational workloads in cloud environments.

As organisations increasingly depend on cloud services, protecting information and maintaining secure configurations are essential.

The purpose of this assessment was to identify common cloud security risks, understand the shared responsibility model, and recommend security controls that could help HanTech protect its cloud infrastructure and information assets.

**Assessment approach:** This section is based on security research and risk analysis. It was not an independent technical scan or penetration test of a live cloud environment.

## 2. Potential Cloud Security Risks

The following risks were considered relevant to HanTech's assumed cloud environment.

### 2.1 Cloud Misconfiguration

**Description:** Incorrect cloud configurations, such as publicly accessible storage, exposed management interfaces, or overly permissive network rules.

**Potential impact:**
- Unauthorised access to confidential information.
- Exposure of customer data.
- Increased attack surface.
- Regulatory and reputational consequences.

**Recommended controls:**
- Apply secure configuration baselines.
- Restrict public access to storage and services.
- Review firewall and network security rules.
- Conduct regular cloud configuration assessments.
- Enable alerts for unauthorised configuration changes.

### 2.2 Weak Authentication and Credentials

**Description:** Weak passwords, compromised credentials, and insufficient authentication controls can allow unauthorised users to access cloud resources.

**Potential impact:**
- Account compromise.
- Unauthorised access to business applications.
- Exposure of sensitive information.
- Misuse of administrative privileges.

**Recommended controls:**
- Enforce multi-factor authentication.
- Require strong authentication.
- Apply conditional access controls where available.
- Monitor suspicious login attempts.
- Protect and rotate credentials and secrets.

### 2.3 Excessive User Permissions

**Description:** Users or service accounts may have more permissions than necessary to perform their duties.

**Potential impact:**
- Unauthorised modification or deletion of resources.
- Privilege misuse.
- Increased impact if an account is compromised.

**Recommended controls:**
- Implement role-based access control.
- Apply the principle of least privilege.
- Review permissions regularly.
- Remove unnecessary privileges.
- Use separate accounts for routine and administrative activities.

### 2.4 Unencrypted Data

**Description:** Sensitive information may be exposed if it is not adequately protected while stored or transmitted.

**Potential impact:**
- Exposure of confidential information.
- Loss of customer trust.
- Potential legal or regulatory consequences.

**Recommended controls:**
- Encrypt sensitive data at rest.
- Use secure protocols to protect data in transit.
- Manage encryption keys securely.
- Restrict access to sensitive information.
- Establish data classification and retention requirements.

### 2.5 Insecure APIs

**Description:** Cloud applications may expose APIs with weak authentication, inadequate authorisation, or insufficient input validation.

**Potential impact:**
- Unauthorised access to application functions.
- Exposure or manipulation of data.
- Abuse of application resources.

**Recommended controls:**
- Enforce strong API authentication and authorisation.
- Validate input and handle errors securely.
- Use secure transport encryption.
- Apply rate limiting where appropriate.
- Monitor API access and unusual activity.

### 2.6 Insider Threats

**Description:** Employees, contractors, or other authorised users may intentionally or accidentally misuse their access.

**Potential impact:**
- Unauthorised disclosure of information.
- Accidental data deletion.
- Misuse of privileged access.
- Business disruption.

**Recommended controls:**
- Apply least privilege.
- Monitor privileged activities.
- Review access rights regularly.
- Establish acceptable use and data handling policies.
- Conduct security awareness training.
- Maintain appropriate employee access removal procedures.

### 2.7 Distributed Denial of Service (DDoS)

**Description:** Attackers may overwhelm publicly accessible services with excessive traffic, making them unavailable to legitimate users.

**Potential impact:**
- Service disruption.
- Loss of customer access.
- Operational and financial consequences.
- Damage to organisational reputation.

**Recommended controls:**
- Use cloud provider DDoS protection services.
- Apply network traffic filtering.
- Configure rate limiting and traffic management.
- Monitor unusual traffic patterns.
- Develop an incident response procedure for service disruption.

## 3. Shared Responsibility Model

Cloud security is a shared responsibility between the cloud service provider and the organisation using the service.

The exact division of responsibilities depends on the cloud service model and provider.

### Cloud Service Provider Responsibilities

Depending on the service model, the provider is generally responsible for areas such as:

- Physical security of data centres.
- Security of underlying infrastructure.
- Physical network and hardware protection.
- Security of managed cloud services.
- Infrastructure availability and resilience.

### HanTech Responsibilities

HanTech would remain responsible for areas such as:

- Managing user identities and access permissions.
- Protecting organisational data.
- Configuring cloud resources securely.
- Enforcing authentication requirements.
- Managing application security.
- Monitoring cloud activity.
- Maintaining backups and incident response procedures.

### Why Shared Responsibility Matters

Using a cloud provider does not mean that the organisation transfers all security responsibilities to that provider.

HanTech must understand which controls it is responsible for implementing and monitoring to prevent security gaps.

## 4. Identity and Access Management (IAM)

Identity and Access Management is essential for controlling who can access cloud resources and what actions they can perform.

The following IAM controls are recommended.

### Authentication

Authentication verifies the identity of a user or service.

Recommended measures:
- Enforce multi-factor authentication.
- Use strong authentication methods.
- Protect privileged accounts.
- Monitor failed and suspicious login attempts.

### Authorisation

Authorisation determines what an authenticated identity is permitted to access or perform.

Recommended measures:
- Apply role-based access control.
- Enforce least privilege.
- Separate administrative and standard user accounts.
- Review access permissions regularly.

### Auditing and Accountability

Auditing provides records of user and system activities.

Recommended measures:
- Enable cloud audit logging.
- Monitor administrative activities.
- Retain logs according to organisational requirements.
- Investigate suspicious access and configuration changes.

## 5. Recommended Cloud Security Controls

| Security Area | Recommended Control | Expected Benefit |
|---|---|---|
| Identity security | MFA and strong authentication | Reduces account compromise |
| Access management | Least privilege and RBAC | Limits excessive permissions |
| Data protection | Encryption at rest and in transit | Protects sensitive information |
| Network security | Firewalls and network segmentation | Reduces unauthorised access |
| Configuration management | Secure configuration baselines | Reduces misconfiguration |
| API security | Authentication and input validation | Protects application interfaces |
| Monitoring | Centralised logging and alerting | Improves threat detection |
| Availability | DDoS protection and backups | Improves service resilience |
| Vulnerability management | Regular scanning and patching | Reduces exposure to known weaknesses |

## 6. Regulatory and Compliance Considerations

HanTech should identify the legal, regulatory, and contractual requirements that apply to its operations, customers, and the information it processes.

Relevant frameworks and regulations may include:

### Nigeria Data Protection Act (NDPA) 2023

Where applicable, HanTech should protect personal data and establish appropriate technical and organisational security measures.

### General Data Protection Regulation (GDPR)

GDPR may apply where HanTech's processing activities fall within its territorial scope. Relevant requirements include protecting personal data and maintaining appropriate security measures.

### Health Insurance Portability and Accountability Act (HIPAA)

HIPAA is relevant only if HanTech operates as a covered entity or business associate handling protected health information within the scope of the law.

### Payment Card Industry Data Security Standard (PCI DSS)

PCI DSS may apply if HanTech stores, processes, or transmits payment card data, or if its systems affect the security of the cardholder data environment.

Compliance obligations should be confirmed through a proper assessment of HanTech's business activities and applicable requirements.

## 7. Cloud Security Governance Recommendations

To maintain a secure cloud environment, HanTech should:

1. Establish a cloud security policy.
2. Maintain an inventory of cloud assets and services.
3. Assign responsibility for cloud security controls.
4. Conduct periodic risk assessments.
5. Review IAM permissions regularly.
6. Monitor cloud logs and security alerts.
7. Maintain tested backup and recovery procedures.
8. Assess third-party cloud providers.
9. Conduct regular vulnerability and configuration assessments.
10. Review compliance obligations as the business evolves.

## 8. Conclusion

The cloud security assessment highlights the importance of securing cloud environments through a combination of technical controls, governance, and continuous monitoring.

The shared responsibility model makes it clear that cloud providers and customers have different but complementary security obligations.

For HanTech, effective IAM, secure configuration, encryption, monitoring, and vulnerability management would help reduce exposure to common cloud security risks.

This assessment also reinforces the connection between technical cybersecurity and GRC: security controls must be supported by clear policies, assigned responsibilities, risk management, and compliance oversight.
