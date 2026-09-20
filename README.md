# Network Security Monitoring Design

## Overview

This project documents a university security-monitoring design exercise completed as part of my BSc Ethical Hacking and Cybersecurity degree.

The task was to act as a **network security evaluation specialist** and propose an effective monitoring solution for a complex enterprise network. The work focused on telemetry collection, detection of reconnaissance and anomalous activity, IDS/IPS design considerations, SIEM-style log analysis, APT detection, operational impact and cost.

> **Important:** this was a **design and evaluation project**, not a production ELK deployment. The repository presents the architecture and detection ideas I proposed at the time.

## Project Goals

- Decide what network and endpoint data should be collected
- Prioritise monitoring around critical assets
- Detect internal reconnaissance and suspicious traffic patterns
- Evaluate session, statistical, alert and full-packet data
- Propose an ELK-based monitoring approach
- Compare Snort and Suricata
- Consider APT detection and exfiltration indicators
- Account for scalability, cost and business operations

## Proposed Monitoring Approach

### 1. Telemetry Strategy

The design considered four main data types:

| Data Type | Intended Use |
|---|---|
| Full packet data | Detailed investigation around critical assets and live incidents |
| Session data | Source/destination IPs, ports, timestamps and communication metadata |
| Statistical data | Detect unusual changes in traffic volumes and behaviour |
| Alert data | IDS/IPS and monitoring-generated events requiring review |

Full-packet capture was proposed selectively around critical server assets rather than across the whole environment because of storage, processing and legal constraints.

### 2. ELK and Beats

The proposed monitoring stack centred on **Elasticsearch, Logstash and Kibana (ELK)**, with Beats used for different telemetry sources:

- Filebeat
- Winlogbeat
- Packetbeat
- Auditbeat

The design used Packetbeat as the main network-traffic analysis component for session and statistical data, with Kibana-style visualisation and centralised analysis.

### 3. Detection Use Cases

Examples considered in the original design included:

- Unusual access attempts against privileged resources
- High volumes of outbound traffic that could indicate exfiltration
- Abnormal numbers of DNS requests
- DoS-style traffic anomalies
- Unexpected increases in wireless devices
- Internal reconnaissance against critical servers
- APT-related behaviour requiring analyst review

More detail is available in [docs/detection-use-cases.md](docs/detection-use-cases.md).

### 4. Snort vs Suricata

The project compared Snort and Suricata as network intrusion-detection options.

The original analysis discussed rule compatibility, file inspection, protocol identification, multithreading and ease of configuration. Suricata was presented as the stronger fit for the proposed environment at the time of the assessment.

### 5. SOC and Business Considerations

The design also considered the operational side of security monitoring:

- communication between the SOC and the wider business
- ITSM / ITIL processes
- staff capability and training
- scalability of high-volume monitoring
- cost of running and maintaining the monitoring stack
- external penetration testing as part of security assurance

## Skills Demonstrated

- Network security monitoring
- Telemetry planning
- IDS/IPS concepts
- Log-analysis architecture
- ELK / Beats concepts
- Packetbeat
- Detection engineering fundamentals
- Network anomaly analysis
- SOC operations awareness
- Security architecture evaluation
- Technical research and reporting

## Retrospective

This project was completed during university and reflects my understanding at that time.

With my current cybersecurity knowledge, I would improve the design by:

- separating SIEM, NDR, IDS and IPS responsibilities more clearly
- validating product capabilities against current documentation
- mapping detections to MITRE ATT&CK techniques
- defining clearer alert logic and analyst triage steps
- using structured logging and retention requirements
- adding explicit data-flow and sensor-placement diagrams
- distinguishing prevention controls from detection controls
- designing measurable detection and response objectives

I would also avoid presenting older pricing or product-specific assumptions as current facts without re-validating them.

The original coursework has not been rewritten to claim deployment or hands-on implementation that did not occur.

## Repository Structure

```text
.
├── README.md
└── docs/
    ├── telemetry-strategy.md
    └── detection-use-cases.md
```
