# Threat-to-Telemetry Matrix

This matrix converts the original report's monitoring ideas into a clearer SOC-style view of **threat → telemetry → detection idea → analyst action**.

| Threat / Scenario | Telemetry from Original Design | Detection Idea | Analyst Action |
|---|---|---|---|
| Internal reconnaissance | Session data, IDS/IPS alerts, Packetbeat-style network telemetry | One internal host probing multiple systems, ports or critical services | Review source host, destination systems and associated user activity |
| Suspicious access to privileged resources | Session data and Packetbeat | Unexpected or repeated attempts to reach high-privilege resources | Validate whether access is legitimate and investigate the source endpoint |
| Possible data exfiltration | Statistical data and outbound network traffic | Unusually high volume of data leaving the network | Inspect destinations, session history and affected host activity |
| Abnormal DNS activity | Statistical and session data | Unusual number of DNS requests from a host or server | Investigate the host and surrounding network activity |
| Denial-of-service pattern | Statistical network data | Sharp increase in traffic volume or abnormal packet behaviour | Confirm whether the event is malicious and protect affected services |
| Unexpected wireless devices | Device / network statistical data | Unusual rise in devices joining the wireless network | Check against authorised devices and BYOD policy |
| Potential long-term intrusion / APT activity | Centralised logs, Packetbeat and unusual outbound behaviour | Persistent anomalous activity or data movement requiring correlation | Escalate for deeper investigation and correlate across available logs |

## Important Limitation

These are **design-level detection ideas from the original coursework**. They were not implemented, tuned or validated against live production data.