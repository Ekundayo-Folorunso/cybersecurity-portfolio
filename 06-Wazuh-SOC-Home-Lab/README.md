# Wazuh SOC Home Lab

## Project Overview

This project documents the design, deployment, configuration, troubleshooting, and security monitoring of a hands-on **Security Operations Center (SOC) home lab** using Wazuh.

The lab was built to develop practical experience in:

- SIEM monitoring
- Security alert investigation
- Log analysis
- Endpoint monitoring
- Threat hunting
- File Integrity Monitoring (FIM)
- Authentication event analysis
- Privilege activity investigation
- Network security monitoring
- Security troubleshooting

---

## Lab Architecture

The environment consists of two virtual machines running in VirtualBox.

| Component | Role |
|---|---|
| Kali Linux | Wazuh Server / SOC Monitoring Platform |
| Ubuntu Server | Monitored Endpoint |
| Wazuh Manager | Security event management |
| Wazuh Agent | Endpoint data collection |
| Wazuh Indexer | Security data storage and search |
| Wazuh Dashboard | Security monitoring and visualization |
| Filebeat | Log forwarding |
| OpenSearch | Security data indexing and search |
| Suricata | Network intrusion detection |
| VirusTotal | Threat intelligence enrichment |
| Wireshark | Network traffic and PCAP analysis |

---

## Lab Objectives

The main objectives of this project were to:

1. Build a functional SOC monitoring environment.
2. Deploy and configure Wazuh.
3. Connect an Ubuntu endpoint to the Wazuh Manager.
4. Collect and analyze security logs.
5. Monitor authentication activity.
6. Monitor privilege-related activity.
7. Detect file changes using File Integrity Monitoring.
8. Integrate network security monitoring.
9. Perform threat hunting.
10. Troubleshoot SIEM services, connectivity, log ingestion, and dashboard issues.
11. Document investigations and lessons learned.

---

## Technologies & Tools

### SIEM & Security Monitoring

- Wazuh
- Wazuh Manager
- Wazuh Agent
- Wazuh Indexer
- Wazuh Dashboard

### Log Collection & Search

- Filebeat
- OpenSearch

### Network Security

- Suricata
- Wireshark
- PCAP analysis

### Threat Intelligence

- VirusTotal

### Operating Systems

- Kali Linux
- Ubuntu Server

### Virtualization

- VirtualBox

---

## Wazuh Deployment

The Wazuh environment was deployed on Kali Linux with an Ubuntu Server endpoint acting as the monitored agent.

### Wazuh Server

The Wazuh server environment included:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard
- Filebeat

### Wazuh Endpoint

An Ubuntu Server virtual machine was configured with the Wazuh Agent.

The endpoint was registered with the Wazuh Manager and monitored for security events.

---

## Security Monitoring

The lab was used to monitor several types of security activity.

### Authentication Monitoring

Investigated authentication-related events including:

- PAM login sessions
- Login session creation
- Login session closure
- Authentication activity

### Privilege Activity

Investigated events related to elevated privileges, including:

- Sudo activity
- Successful sudo execution
- Privilege-related events

### File Integrity Monitoring

Wazuh File Integrity Monitoring was used to monitor changes to files and directories.

Activities included investigating:

- File creation
- File modification
- File integrity events

---

#### Suricata Network Monitoring

Suricata was deployed on the Ubuntu environment for network security monitoring.

Suricata generated security telemetry through:

`/var/log/suricata/eve.json`

Additional logs included:

- `/var/log/suricata/fast.log`
- `/var/log/suricata/stats.log`
- `/var/log/suricata/suricata.log`

The `eve.json` log was analyzed to investigate network security alerts.

Example activity investigated included Suricata alerts related to network traffic and policy detection.

---

## Wireshark & PCAP Analysis

Wireshark was used to develop practical network traffic analysis skills.

Activities included:

- Opening PCAP files
- Inspecting packets
- Examining TCP/IP traffic
- Identifying network protocols
- Following network conversations
- Investigating suspicious traffic patterns
- Analyzing packet-level evidence

A dedicated Wireshark PCAP investigation will be documented separately in this portfolio.

## VirusTotal Integration

VirusTotal was integrated with Wazuh to provide additional threat intelligence context for selected security events.

The integration was used to support:

- File reputation analysis
- Hash analysis
- Threat intelligence enrichment

Sensitive API credentials are intentionally excluded from this repository.

---

## Threat Hunting

Threat hunting was performed using Wazuh security telemetry.

Investigated events included:

- Authentication activity
- PAM login events
- Sudo activity
- File integrity events
- Security alerts
- Suricata network alerts

The objective was to identify unusual or security-relevant activity and determine whether further investigation was required.

---

## Troubleshooting Case Study

### Wazuh Threat Hunting Returned 0 Hits

#### Problem

The Wazuh Threat Hunting interface initially returned 0 results even though security events were being generated.

#### Investigation

The Wazuh index pattern was investigated to determine whether the correct time field was being used.

The saved index pattern was configured to use:

`timestamp`

However, the actual date field available in the Wazuh alert index was:

`@timestamp`

#### Root Cause

The Threat Hunting interface was using an incorrect time field for the date-based search.

#### Solution

The Wazuh index pattern was updated so that the correct date field was:

`@timestamp`

#### Verification

After correcting the index pattern, Threat Hunting successfully returned security events.

The dashboard subsequently displayed **72 security events**.

Examples included:

- PAM login session opened
- PAM login session closed
- Successful sudo to ROOT executed

#### Lesson Learned

When a SIEM dashboard returns no results even though logs exist, verify:

- The index pattern
- The selected time range
- The timestamp field
- Field mappings
- Data ingestion
- Index availability

---

## Troubleshooting Experience

During development of this SOC lab, several technical issues were investigated and resolved, including:

- Wazuh Indexer installation issues
- Wazuh Agent connectivity problems
- Filebeat service issues
- Log ingestion problems
- TLS/certificate configuration
- Wazuh Dashboard configuration
- Index mapping problems
- Threat Hunting zero-result issues
- Suricata log analysis
- Wazuh log decoder errors
- Virtual machine networking issues

These troubleshooting experiences helped develop practical skills in:

- System administration
- Log investigation
- Configuration analysis
- Service troubleshooting
- Root cause analysis
- Problem solving

---

## Investigation Methodology

Security investigations in this lab follow a structured approach:

**Alert → Investigation → Evidence → Analysis → Root Cause → Response → Verification → Documentation**

The objective is not only to identify an alert but to understand:

- What happened?
- When did it happen?
- Which endpoint was involved?
- What generated the event?
- Was the activity expected or suspicious?
- What evidence supports the conclusion?
- What action should be taken?

---

## Evidence

Supporting evidence for this project will include:

- Wazuh dashboard screenshots
- Terminal output
- Configuration screenshots
- Security alerts
- Threat hunting results
- Suricata alerts
- PCAP analysis
- Troubleshooting records
- Investigation reports
- Standard Operating Procedures

**Security Note:** Passwords, API keys, private keys, certificates, tokens, and other sensitive information will not be published in this repository.

---

## Key Skills Developed

Through this project, I developed practical experience in:

- SIEM monitoring
- Alert investigation
- Log analysis
- Threat hunting
- Endpoint monitoring
- File Integrity Monitoring
- Authentication event analysis
- Privilege activity investigation
- Network traffic analysis
- PCAP analysis
- Suricata IDS monitoring
- Threat intelligence enrichment
- Linux troubleshooting
- Service troubleshooting
- Configuration analysis
- Root cause analysis
- Security documentation

---

## Project Status

**Status: Active / Continuing Development**

This project will continue to grow as additional SOC investigations, PCAP analysis, detection exercises, incident response scenarios, and security monitoring activities are completed.

---

## Author

**Ekundayo Folorunso**

Aspiring Tier 1 SOC Analyst | Cybersecurity

Email: emmymakx@gmail.com
