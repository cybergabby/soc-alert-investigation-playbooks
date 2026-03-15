# Brute Force Login Investigation

## Description
This alert indicates multiple failed login attempts against a user account within a short period of time.

## Possible Threat
Attackers may attempt password guessing or credential stuffing to gain unauthorized access.

## Log Sources
- Active Directory authentication logs
- VPN logs
- Identity provider logs
- SIEM authentication events

## Initial Triage
1. Verify the number of failed login attempts.
2. Identify the source IP address.
3. Determine if multiple accounts were targeted.

## Investigation Steps
1. Query authentication logs for failed login attempts.
2. Check if a successful login occurred after the failures.
3. Analyze the source IP reputation.
4. Check geolocation of the login attempts.
5. Investigate additional activity from the affected account.

## Indicators of Compromise
- Multiple failed logins from a single IP
- Successful login after repeated failures
- Login attempts from unusual locations

## Containment
- Lock the affected account
- Block the malicious IP
- Force password reset

## Remediation
- Enable MFA
- Strengthen password policies

## Detection Improvement
Tune SIEM rules to alert when:
- More than 10 failed logins occur within 5 minutes
