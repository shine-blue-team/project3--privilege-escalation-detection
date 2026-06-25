# Project 3 — Privilege Escalation Detection

## Objective
Simulate a privilege escalation attack chain on a Windows 10 endpoint
and detect account creation, admin group modification, and account
deletion using Splunk Enterprise on Kali Linux.

## Lab Setup
- SIEM: Splunk Enterprise on Kali Linux (Oracle VirtualBox)
- Endpoint: Windows 10 with Splunk Universal Forwarder
- Log source: Windows Security Event Logs

## Attack Simulated
1. Created a backdoor user account (Event ID 4720)
2. Added account to Administrators group (Event ID 4732)
3. Deleted account to cover tracks (Event ID 4726)

## Detection Method
- Wrote SPL queries to detect each stage individually
- Wrote combined attack chain query correlating all 3 event IDs
- Correlated with Project 2 brute force events on same machine

## Alerts Created
- Alert 1: New User Account Created (High severity)
- Alert 2: User Added to Administrators Group (Critical severity)
- Alert 3: User Account Deleted — Possible Cover-Up (Medium severity)

## Result
All 3 alerts triggered successfully in real time. Full attack chain
detected and correlated with brute force activity from Project 2.

## Tools Used
Splunk Enterprise, Splunk Universal Forwarder, Kali Linux, Windows 10
