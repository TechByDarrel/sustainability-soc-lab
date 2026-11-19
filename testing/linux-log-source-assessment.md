# Linux Log Source Assessment

## Environment
- Operating system: Ubuntu 26.04.1 LTS
- Platform: WSL 2
- Init system: systemd

## Authentication Log
- Location: /var/log/auth.log
- Permissions: -rw-r-----
- Owner: syslog
- Group: adm
- Read access verified successfully.

## System Journal
- Utility: journalctl
- Read access verified without sudo.
- Recent system and authentication events were visible.

## Observed Events
- Local user session creation.
- Systemd user-session creation.
- Scheduled root CRON sessions.
- Failed password checks.
- Sudo authentication failures.

## SSH Service
- Service checked: ssh
- Observed state: inactive

No claim is made that SSH authentication events were collected.

## Limitations
- Sudo authentication currently fails for the project user.
- SSH is not active.
- Available records represent local WSL activity.
- These records do not constitute evidence of an external intrusion.

## Conclusion
Ubuntu authentication logging is available and readable, making it suitable for initial SOC log collection and authentication-event analysis.
