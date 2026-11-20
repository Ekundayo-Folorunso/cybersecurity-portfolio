# From Vulnerability to Compliance: Securing Legacy and Cloud Systems at HanTech

## Project Overview

This project was undertaken as part of a cybersecurity capstone programme. It focused on assessing security weaknesses in a simulated legacy IT environment and developing practical recommendations to improve an organisation's security posture.

Working as part of a cybersecurity consulting team, we used Greenbone/OpenVAS to identify and assess vulnerabilities in a Metasploitable 2 training environment. We examined the possible impact of the identified weaknesses and recommended security controls, Governance, Risk and Compliance (GRC) policies, and cloud security practices to reduce organisational risk.

The project demonstrates how technical vulnerability assessment can be translated into business risk analysis and actionable security recommendations.

## Project Objectives

- Identify security vulnerabilities in a simulated legacy IT environment.
- Perform vulnerability assessment using Greenbone/OpenVAS.
- Evaluate the likelihood and potential impact of identified vulnerabilities.
- Recommend appropriate technical security controls.
- Develop GRC policies to address identified security weaknesses.
- Examine cloud security responsibilities, threats and compliance considerations.
- Communicate findings and recommendations in a format suitable for management.

## Tools and Technologies

- Greenbone/OpenVAS
- Metasploitable 2
- Vulnerability Assessment
- Risk Assessment
- Security Control Analysis
- Governance, Risk and Compliance (GRC)
- Cloud Security Fundamentals

## Key Findings

Five vulnerabilities were selected for detailed assessment:

1. MySQL Root Account with Empty Password.
2. vsftpd 2.3.4 Compromised Source-Package Backdoor.
3. rlogin Passwordless Root Access.
4. DistCC Remote Code Execution.
5. Apache Tomcat Manager Default Credentials.

The findings highlighted weaknesses involving authentication, privileged access, insecure services, software integrity and remote command execution.

## Project Deliverables

| Document | Description |
|---|---|
| 01 – Project Overview and Methodology | Project background, objectives, scope and approach. |
| 02 – OpenVAS Vulnerability Assessment | Scanner process, assessment evidence and scan observations. |
| 03 – Vulnerability Findings | Detailed explanation of the five selected vulnerabilities. |
| 04 – Risk Assessment | Likelihood, impact, CVSS and overall risk ratings. |
| 05 – Security Control Recommendations | Recommended controls and how they reduce risk. |
| 06 – GRC Policy Recommendations | Policies to improve governance and security management. |
| 07 – Cloud Security Assessment | Shared responsibility, IAM, MFA, cloud threats and compliance. |
| 08 – Executive Summary | Key findings and recommendations for management. |
| 09 – Conclusion and Lessons Learned | Project outcomes and lessons from the assessment. |
| 10 – My Individual Contribution | My leadership, technical activities and personal learning. |

## My Role and Contribution

I served as the group leader and helped coordinate the team's activities throughout the capstone project.

My contributions included:

- Coordinating group activities and helping members understand their assigned responsibilities.
- Performing the Greenbone/OpenVAS vulnerability assessment against the simulated training environment.
- Reviewing the scan results and identifying security weaknesses.
- Selecting five critical vulnerabilities for detailed assessment.
- Analysing the potential impact of the vulnerabilities on the organisation.
- Contributing to the risk assessment and recommended security controls.
- Helping translate technical findings into practical GRC policy and management recommendations.

This project strengthened my understanding of vulnerability assessment, security risk management, governance and the relationship between technical security controls and organisational protection.

## Project Scope and Important Note

The vulnerability assessment was performed against a simulated training environment using Metasploitable 2. The identified findings relate to that lab environment and are not confirmation of vulnerabilities in a real organisation's production infrastructure.

The cloud security section provides recommendations and considerations for HanTech's hypothetical cloud environment; it was not a cloud penetration test or a confirmed cloud vulnerability assessment.

## Key Learning Outcomes

Through this project, I developed a stronger understanding of:

- Vulnerability identification and assessment.
- Interpreting OpenVAS findings and CVSS severity scores.
- Assessing likelihood, impact and organisational risk.
- Recommending preventive and detective security controls.
- Developing practical GRC policies.
- Understanding cloud security responsibilities and IAM.
- Communicating technical security findings to non-technical stakeholders.

## Project Evidence

Supporting screenshots, scan observations and assessment evidence are organised in the `evidence/` folder.

## Conclusion

This project reinforced an important lesson: identifying vulnerabilities is only the beginning of effective cybersecurity. Organisations must understand the risks, implement appropriate controls, establish clear policies and continuously monitor their systems.

The experience helped me connect technical vulnerability assessment with governance, risk management and business security objectives.
