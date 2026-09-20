# Snort vs Suricata

## Purpose

As part of the original monitoring-design exercise, I compared **Snort** and **Suricata** as network intrusion-detection options for the proposed environment.

The comparison was based on the research and product capabilities I reviewed at the time of the 2022 assessment.

## Areas Compared

### Rule Ecosystem

Snort had the advantage of a long-established rule ecosystem and broad industry adoption.

The original report noted that Suricata could also make use of many rules associated with established Snort ecosystems, while extending them with its own functionality.

### File Inspection

The coursework highlighted Suricata's ability to inspect and log files transferred over protocols such as HTTP, FTP and SMTP.

### Application-Layer Identification

The original analysis treated Suricata's protocol detection as more flexible because it could identify application protocols without depending entirely on expected port numbers.

### Multithreading and Performance

The report also considered Suricata's multithreaded architecture a benefit for a network expected to generate high volumes of traffic. Snort 3 was noted as improving in this area compared with earlier Snort versions.

## Original Conclusion

For the university design, I selected **Suricata** as the stronger fit for the proposed monitoring environment.

That conclusion reflected the sources and software landscape reviewed at the time and should not be treated as a current universal recommendation.

## Current Reflection

Today I would compare both tools against the exact throughput and traffic profile of the environment, current feature sets, rule-management requirements, integration with the wider logging stack, analyst familiarity, operational overhead and detection-validation results.

The key lesson from the original comparison was not simply choosing one product over another, but evaluating monitoring technology against the needs of the environment.