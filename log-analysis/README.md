# Log Analysis and SIEM Mini Lab

This project demonstrates basic log analysis techniques used in Security Operations Center (SOC) environments. Authentication logs were reviewed to identify suspicious activity, investigate potential security incidents, and recommend appropriate response actions.

## Objective
Analyze Linux authentication logs to identify indicators of compromise and simulate the investigative process of a SOC analyst.

## Data Source
Linux authentication logs (auth.log) obtained from publicly available sample data.

## Analysis Overview
The logs were reviewed manually to identify authentication events, privilege escalation, and system-level command execution. The analysis focused on understanding the sequence of events following remote access to the system.

## Key Observations
A successful SSH login was observed from an external IP address. Following authentication, the user obtained root-level privileges and executed multiple administrative commands. These commands included installing software packages and configuring a service to persist across system reboots.

## Evidence Samples
```
Accepted publickey for ubuntu from 85.245.107.41 port 54259 ssh2
pam_unix(sshd:session): session opened for user ubuntu by (uid=0)
sudo: ubuntu : USER=root ; COMMAND=/usr/bin/apt-get install filebeat
sudo: ubuntu : USER=root ; COMMAND=/usr/sbin/update-rc.d filebeat defaults
```

## Incident Summary
The log data indicates remote access to the system followed by privilege escalation and post-authentication activity consistent with system modification. While the activity could represent legitimate administrative behavior, the pattern aligns with common post-compromise techniques and would require validation in a production environment.

## Recommended Response
Confirm whether the SSH access originated from an authorized administrator. Review the source IP address and login method. Validate the legitimacy of installed software and persistence mechanisms. Restrict SSH access where possible and enforce stronger authentication controls such as multi-factor authentication. Continue monitoring authentication and privilege escalation logs for additional suspicious behavior.

## Tools Used
Manual log analysis and grep
