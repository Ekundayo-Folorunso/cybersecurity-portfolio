# 01 – Project Overview and Methodology

## 1. Project Background

HanTech is a simulated medium-sized technology company that operates legacy IT systems alongside cloud-hosted infrastructure and data services.

As organisations increasingly depend on technology to deliver services and manage business information, weaknesses in their IT environments can expose them to cyberattacks, data breaches, operational disruption and regulatory risks.

This project, titled **"From Vulnerability to Compliance: Securing Legacy and Cloud Systems at HanTech,"** was undertaken as part of a cybersecurity capstone programme.

Our team worked from the perspective of junior cybersecurity consultants. The objective was to identify security weaknesses in a simulated legacy environment, assess their potential impact on the organisation and recommend appropriate technical controls and Governance, Risk and Compliance (GRC) measures.

The project also considered how the security principles identified in the legacy assessment could guide the protection of HanTech's cloud environment.

## 2. Project Objectives

The main objectives were to:

- Identify security vulnerabilities within a simulated legacy IT environment.
- Perform a vulnerability assessment using Greenbone/OpenVAS.
- Review scan results and select significant vulnerabilities for detailed analysis.
- Assess the likelihood and potential organisational impact of each selected vulnerability.
- Recommend security controls to reduce identified risks.
- Develop GRC policies that support consistent security practices.
- Examine cloud security principles, common threats and relevant compliance requirements.
- Present findings and recommendations in a format suitable for management.

## 3. Assessment Scope

The technical assessment focused on a simulated legacy system running in a controlled training environment.

| Assessment Item | Details |
|---|---|
| Organisation | HanTech (simulated company) |
| Target Environment | Metasploitable 2 training system |
| Target IP Address | 10.0.2.5 |
| Vulnerability Assessment Tool | Greenbone/OpenVAS |
| Assessment Type | Vulnerability assessment |
| Main Focus | Identification, analysis and risk evaluation |
| Selected Findings | Five critical vulnerabilities |

The project also included a conceptual review of cloud security risks and recommendations. The cloud environment was not independently scanned or penetration-tested as part of this assessment.

## 4. Tools and Technologies

### Greenbone/OpenVAS

Greenbone/OpenVAS was used to scan the target training system for known security weaknesses, exposed services and potentially exploitable vulnerabilities.

The scan results provided technical information, including affected services, network ports, vulnerability descriptions, severity ratings, CVSS scores and quality-of-detection information.

### Metasploitable 2

Metasploitable 2 provided a deliberately vulnerable training environment for conducting security assessment activities in a controlled and authorised lab.

It allowed the team to examine realistic examples of insecure services, weak credentials and software vulnerabilities without targeting a production system.

## 5. Assessment Methodology

The project followed a structured vulnerability assessment and risk analysis process.

### Step 1: Understanding the Environment

We reviewed the project scenario and identified the simulated organisation's legacy and cloud security considerations.

We established the scope of the technical assessment and identified the training system to be assessed.

### Step 2: Vulnerability Scanning

Greenbone/OpenVAS was used to scan the Metasploitable 2 target at 10.0.2.5.

The scanner examined available services and reported potential vulnerabilities based on its vulnerability tests and collected evidence.

### Step 3: Reviewing and Selecting Findings

We reviewed the scan output and selected five critical findings for detailed assessment.

The selection considered reported severity, available scanner evidence, affected services and potential consequences for the organisation.

### Step 4: Risk Assessment

Each selected vulnerability was assessed using:

- Likelihood: How likely the weakness could be exploited in the assessed environment.
- Impact: The potential consequences for the organisation if exploitation succeeded.
- Risk Rating: The team's overall assessment based on likelihood and impact.

CVSS scores from the scanner were used as technical severity references, not as automatic substitutes for business risk ratings.

### Step 5: Security Control Recommendations

We recommended practical security controls to address each vulnerability. These included stronger authentication, restricted access, secure remote access, software replacement, patching and least privilege.

### Step 6: GRC Policy Recommendations

We developed policies covering access control, password and authentication, patch and software lifecycle management, vulnerability management, remote access and network security, and logging and security monitoring.

### Step 7: Cloud Security Review

We examined shared responsibility, Identity and Access Management (IAM), Multi-Factor Authentication (MFA), least privilege, common cloud threats, security best practices and potentially applicable compliance requirements.

### Step 8: Reporting and Recommendations

The findings, risk assessments and recommendations were organised into a structured report, including an executive summary for non-technical management.

## 6. Vulnerability Selection Criteria

Five vulnerabilities were selected from the OpenVAS scan for detailed analysis.

The selection was based on:

1. The severity reported by the scanner.
2. The evidence available to support each finding.
3. The level of access or exploitation opportunity presented.
4. The possible impact on confidentiality, integrity and availability.
5. The relevance of the finding to HanTech's security controls and policies.

The five selected findings involved MySQL, vsftpd, rlogin, DistCC and Apache Tomcat.

## 7. Assessment Limitations

This project used a deliberately vulnerable training environment. Therefore, the findings describe the assessed lab system and should not be interpreted as confirmed weaknesses in a real company's production infrastructure.

The cloud security recommendations were based on the project scenario and cloud security fundamentals. They were not the result of a separate cloud vulnerability scan.

Risk ratings were preliminary team assessments and would require validation against actual business operations, asset criticality, network exposure and existing controls before being used for a real organisation.

## 8. Project Outcome

The assessment provided a practical understanding of how technical vulnerabilities can create organisational risks.

It also demonstrated how vulnerability findings can be translated into security controls, GRC policies and management recommendations.

The project helped connect technical cybersecurity activities with governance, risk management and business protection.
