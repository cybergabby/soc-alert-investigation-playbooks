# Investigation Queries

## Splunk – Failed Login Attempts

index=auth_logs action=failure
| stats count by user, src_ip
| where count > 10

## Splunk – Successful Login After Failures

index=auth_logs action=success
| stats count by user, src_ip

## Suspicious PowerShell Execution

index=sysmon EventCode=1
Image="*powershell.exe*"
CommandLine="*-enc*"
