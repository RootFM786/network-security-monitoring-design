# Detection Use Cases

The following use cases were proposed in the original university monitoring design.

## Internal Reconnaissance

Monitor traffic around critical server infrastructure for scanning and unusual connection attempts originating from inside the network.

**Useful telemetry:**
- session metadata
- IDS alerts
- network flow / Packetbeat data
- selected packet capture around critical assets

## Suspicious Privileged-Resource Access

Identify endpoints repeatedly trying to access restricted or high-privilege resources.

**Potential response:**
- generate an IDS alert
- review the related session data
- investigate source host and account activity

## Potential Data Exfiltration

Detect unusually high volumes of outbound traffic that do not match expected network behaviour.

**Potential indicators:**
- abnormal transfer volume
- repeated outbound connections
- unexpected destination systems

## Abnormal DNS Activity

Identify an unusual increase in DNS requests from a host or server.

The original design treated this as an example of statistical data that could trigger further investigation using session-level evidence.

## Denial-of-Service Patterns

Monitor for sharp changes in traffic volume and abnormal packet behaviour that could indicate denial-of-service activity.

## Unexpected Wireless Devices

Monitor for an unusual increase in devices joining the wireless network, which could indicate a breach of organisational BYOD policy or unauthorised access.

## APT / Long-Term Intrusion Indicators

The design proposed using centralised monitoring and Packetbeat-style traffic analysis to identify unusual outbound data volumes and other patterns that could warrant investigation for espionage or long-term compromise.

## Analyst Review

The original design assumed suspicious events would be escalated for human review rather than relying entirely on automated blocking.

This is an important distinction: these were **proposed detection use cases**, not detections that were built and validated in a live environment.
