# ELK Monitoring Design

## Overview

The original coursework proposed an **ELK-based monitoring architecture** to centralise and analyse security telemetry.

The design centred on Elasticsearch for search and analysis, Logstash for processing, Kibana for visualisation, and Beats for collecting endpoint and network telemetry.

> This was a proposed architecture rather than a live deployment.

## Proposed Data Sources

### Filebeat

Used in the design for collecting log-file data from systems and applications.

### Winlogbeat

Included for Windows event-log collection.

### Packetbeat

Packetbeat was the main network-focused component in the design. It was proposed for analysing session and statistical network data, especially around privileged-resource access, unusual outbound traffic and suspicious activity around critical assets.

### Auditbeat

Included as an additional host-level source for audit and system activity.

## Monitoring Flow

Endpoints / Network → Beats collection → Processing / ingestion → Elasticsearch → Kibana → Analyst investigation

The original report also referenced X-Pack capabilities for monitoring and reporting within the Elastic ecosystem.

## Selective Collection

A core part of the design was avoiding unnecessary full-packet collection across the entire network. Instead, the proposal was to collect richer evidence around critical server assets, lighter-weight session/statistical/alert data more broadly, and increase collection depth during live incident investigation.

## Proposed Analyst Use

The architecture was intended to support investigation of internal reconnaissance, suspicious privileged-resource access, data-exfiltration indicators, unusual DNS behaviour, denial-of-service patterns, unexpected wireless activity and longer-term anomalous behaviour associated with possible APT activity.

## Current Reflection

With my current knowledge, I would make the architecture more explicit by defining exact log sources, field requirements, ingestion paths, parsing rules, retention periods, alert thresholds, analyst triage procedures, false-positive tuning and validation requirements.

I would also re-check every product-specific capability against current Elastic documentation before implementing the design.