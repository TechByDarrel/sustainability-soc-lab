# Response Playbook
1. Triage - Check Triggered Alerts in Splunk Cloud, confirm src_ip/user/time
2. Contain - Block IP (INC-001) / Disable account (INC-002)
3. Investigate - Run DET-001 to DET-008, check surrounding 60 min
4. Eradicate - Reset passwords, remove backup access, patch
5. Recover - Re-enable account only after review, monitor 7 days
6. Lessons Learned - Document in incident-report.md
