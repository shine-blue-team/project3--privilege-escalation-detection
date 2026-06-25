# Incident Report — Privilege Escalation Attack

Date: [15.06.2026]
Severity: high
Analyst: [Shine Jason Enock]
Machine: Windows 10 Endpoint

## Summary
A privilege escalation attack was detected on Windows 10 endpoint.
A backdoor account was created and added to the Administrators group,
granting full system access. The account was subsequently deleted in
an attempt to cover tracks. All activity was captured by Splunk SIEM.

## Attack Timeline
- Event 4720: Backdoor account created
- Event 4732: Account added to Administrators group
- Event 4726: Account deleted to cover tracks
- Splunk alerts fired — all 3 stages detected

## Indicators of Compromise
- Event IDs: 4720, 4732, 4726
- Account Created: backdooruser
- Group Modified: Administrators
- Machine: Windows 10 Endpoint

## Connection to Previous Project
Brute force attack detected on same machine before this event.
Full attack chain: Brute Force → Initial Access → Privilege Escalation

## Recommended Actions
1. Remove account from Administrators group immediately
2. Investigate the account that created the backdoor user
3. Reset all admin account passwords
4. Check for files or tasks created by the backdoor account
5. Isolate machine from network pending full investigation

## Outcome
Simulation confirmed. All 3 alerts triggered correctly.
Detection pipeline verified end to end.
