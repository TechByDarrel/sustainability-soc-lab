# Sustainability SOC - Incident Report
Dataset: Synthetic test data - sustainability-soc-lab - clearly labelled synthetic=true
SIEM: Splunk Cloud Platform Trial - prd-p-10393.splunkcloud.com
Sources: auth (120), web (100), firewall (80) + 1 HEC test = 301 events

## INC-001 - External Brute Force + Port Scan - HIGH - BLOCKED
Attacker: 45.155.204.11 -> Target: 10.0.0.31 / soc-workstation-01
Evidence: DET-001 20 failed admin logins, DET-005 20 distinct ports, DET-006 20 blocks, DET-002 0 successes
MITRE: T1110.001 Password Guessing, T1595.002 Vulnerability Scanning
Response: Block IP, reset admin password, review firewall logs

## INC-002 - Insider Exfiltration Pattern - HIGH - INVESTIGATE
User: tunde from 10.0.0.12
Evidence: DET-003 10x 87-145MB downloads, DET-004 /admin/backup.zip, DET-008 curl/8.0, total ~1.2GB
MITRE: T1078 Valid Accounts, T1048 Exfiltration, T1005 Data from Local System
Response: Suspend account pending review, restrict /admin/backup.zip, audit backup contents

## Tuning
DET-007 threshold 10: normal users 1-3 failures, attacker 24 - false positive rate ~0% on synthetic data
