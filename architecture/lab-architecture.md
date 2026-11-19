# Lab Architecture

## 1. Purpose

This document describes the planned architecture for the Sustainability SOC Detection & Response project.

The architecture is provisional and will be updated as implementation decisions are made.

## 2. Host Environment

| Component | Specification |
|---|---|
| Host OS | Windows 11 |
| CPU | Intel Core i7-6600U |
| Physical CPU cores | 2 |
| Logical processors | 4 |
| Installed RAM | 16 GB |
| Free Windows storage at assessment | 92.9 GB |
| Virtualisation | Enabled |
| Linux environment | Ubuntu 26.04.1 LTS |
| Linux platform | WSL 2 |
| Virtualisation software | VirtualBox |

## 3. Available WSL Resources

At the time of assessment:

- WSL reported 7.7 GiB total memory.
- Approximately 7.2 GiB was available.
- Swap allocation was 2 GiB.
- Four logical processors were visible to WSL.

These values may change depending on Windows resource usage and WSL configuration.

## 4. Planned Log Sources

### Windows

Source: Windows Security Event Logs.

Purpose:
- Authentication monitoring.
- Account-management monitoring.
- Security-related event investigation.

### Ubuntu

Source: Linux authentication records and relevant system logs.

Purpose:
- Login monitoring.
- Authentication failure investigation.
- Privilege-related event analysis.

### Web Server

Source: Nginx access and error logs.

Purpose:
- HTTP request monitoring.
- Suspicious request investigation.
- Web-server error analysis.

## 5. Planned Data Flow

Windows Event Logs ─┐

Ubuntu System Logs ─┼──> Log Collection ──> SIEM ──> Detection Rules

Nginx Logs ─────────┘                              │

                                                  v

                                      SOC Dashboard and Alerts

                                                  │

                                                  v

                                     Incident Investigation

                                                  │

                                                  v

                                      Response Documentation

## 6. SIEM Deployment Decision

Decision: Splunk Enterprise Trial on Windows 11 host. Wazuh all-in-one was considered but deferred - it recommends 4 cores / 4GB+ RAM for manager + indexer + dashboard, which exceeds this 2-core lab. ELK deferred for similar overhead (3 services). Splunk provides single-service search, dashboards and alerting in trial, suitable for the Dec 29 deadline. Trial expiry is a documented limitation.

However, the final deployment method will depend on:

- CPU limitations.
- Available RAM.
- Disk capacity.
- Compatibility with the host environment.
- Ability to ingest all three required log sources.
- Availability of the required detection and dashboard features.

A lighter alternative may be selected if a full local Wazuh deployment is impractical.

## 7. Project Data Sources

The project will distinguish between:

1. Actual system logs collected from the local lab.
2. Synthetic logs created for controlled detection testing.
3. Any official datasets subsequently supplied by YuvaIntern.

Synthetic data will never be represented as genuine incident evidence.

## 8. Security and Isolation

- Use only systems and data owned by or authorised for this project.
- Keep testing within the controlled lab.
- Avoid exposing unnecessary services to public networks.
- Protect sensitive information in logs and screenshots.
- Do not publish credentials, tokens or personal information.

## 9. Current Status

Architecture planning only.

Log ingestion, SIEM deployment and detection implementation have not started.
