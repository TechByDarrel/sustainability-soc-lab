# Sustainability SOC Detection & Response

## Project Overview

A defensive cybersecurity project focused on building a small Security Operations Centre (SOC) environment for monitoring, detecting, investigating and responding to suspicious activity.

The scenario represents a fictional manufacturing organisation concerned about the security of its sustainability reporting systems and smart-meter data.

## Objectives

- Collect security logs from at least three sources.
- Centralise and analyse security events.
- Develop and test at least eight detection rules.
- Build a SOC monitoring dashboard.
- Investigate a controlled multi-stage security incident.
- Map observed behaviour to MITRE ATT&CK.
- Produce an incident report and response playbook.

## Planned Log Sources

1. Windows Security Event Logs.
2. Ubuntu authentication logs.
3. Nginx web-server access and error logs.

## Proposed Technology

- Windows 11
- Ubuntu on WSL 2
- Git and GitHub
- Nginx
- Splunk Enterprise Trial (60-day) - selected for lab use based on 2-core / 16GB hardware. Wazuh / ELK deferred as too resource-heavy for this laptop.
- MITRE ATT&CK

SIEM decision: Splunk Enterprise Trial on Windows 11 host. See architecture/lab-architecture.md Section 6 for reasoning.

## Project Data Integrity

Any synthetic security events created for testing or investigation will be explicitly labelled as synthetic.

No simulated findings will be presented as evidence of a real-world compromise.

## Project Structure

- architecture/: Lab design and architecture documentation.
- logs/: Log sources and sample data.
- detections/: Detection rules and documentation.
- dashboard/: Dashboard configuration and evidence.
- investigation/: Incident analysis and MITRE mapping.
- reports/: Incident report and response playbook.
- testing/: Detection testing and validation.
- screenshots/: Project evidence and screenshots.

## Current Progress

- [x] Hardware and environment assessment.
- [x] VirtualBox installation and verification.
- [x] WSL 2 and Ubuntu verification.
- [x] Project directory creation.
- [x] Git repository initialisation.
- [x] Lab architecture documentation.
- [ ] Log collection.
- [ ] SIEM deployment.
- [ ] Detection engineering.
- [ ] Dashboard development.
- [ ] Incident investigation.
- [ ] Final documentation and submission.

## Project Status

Preparation phase. No SIEM has been deployed and no security detections have been implemented yet.
