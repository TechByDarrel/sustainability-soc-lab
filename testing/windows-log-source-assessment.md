# Windows Security Log Source Assessment

## Environment
- Operating system: Windows 11
- Log source: Windows Security
- Log status: Enabled
- Records reported at assessment: 31,677

## Event Availability

| Event ID | Description | Found |
|---|---|---|
| 4624 | Successful logon | Yes |
| 4625 | Failed logon | Yes |
| 4720 | User account created | No |
| 4732 | Member added to security-enabled local group | No |

## Observed Successful Logon

The inspected Event ID 4624 records included:
- Account: SYSTEM
- Logon type: 5 (service logon)
- Process: services.exe
- Provider: Microsoft-Windows-Security-Auditing

These records indicate service logons. They are not evidence of an interactive user login or an intrusion.

## Limitations
- Event IDs 4720 and 4732 were not found in the queried records.
- Their absence does not establish that the corresponding audit policies are disabled.
- Only selected event records were inspected.
- No compromise is inferred from these observations.

## Conclusion
Windows Security logging is enabled and provides successful and failed authentication events suitable for initial SOC analysis.
