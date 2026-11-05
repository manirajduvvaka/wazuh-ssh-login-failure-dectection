SSH Login Failure Detection and Investigation Using Wazuh

Project Type: Cybersecurity / SOC Analyst Lab
Level: Beginner
Status: Completed – Lesson 1

1. Introduction

This project demonstrates how to detect and investigate failed SSH login attempts using Wazuh SIEM on an Ubuntu Server.

The project simulates a failed login attempt and shows how a SOC analyst can investigate the generated security alert.

2. Objectives

- Monitor SSH authentication activity.
- Detect failed login attempts.
- Investigate security alerts in Wazuh.
- Identify the source IP and attempted username.
- Classify security events.

3. Tools Used

Tool| Purpose
Ubuntu Server 24.04| Linux system
Wazuh SIEM| Security monitoring
VirtualBox| Virtual lab
Windows PowerShell| Remote access
SSH| Secure remote connection

4. Lab Environment

- Hostname: "ubuntu-soc-lab"
- Linux username: "socadmin"
- Monitoring platform: Wazuh
- Operating system: Ubuntu Server 24.04

5. Implementation Steps

Step 1: Ubuntu Setup

Installed and configured Ubuntu Server in VirtualBox.

Step 2: SSH Connection

Connected to the Ubuntu server remotely using Windows PowerShell.

Step 3: Generate a Failed Login

Attempted an SSH connection using the non-existent username "wronguser".

The server rejected the authentication attempt.

Step 4: Detect the Alert

Opened the Wazuh Dashboard and navigated to:

"Threat Hunting → Events"

Filtered the events using:

"PAM: User login failed."

Step 5: Investigate the Alert

Observed event details:

Field| Value
Event| PAM: User login failed
Username| wronguser
Source IP| 10.124.173.120
Agent| ubuntu-soc-lab
Rule level| 5
Reason| Attempted login using a non-existent user

6. Security Analysis

Wazuh detected the failed SSH authentication attempt and generated a security alert.

The attempted username did not exist on the Ubuntu server, so authentication was rejected.

The event was classified as Benign / Expected Lab Activity because I intentionally generated it during my own testing.

A failed login does not automatically mean a cyberattack has occurred. Additional investigation is required.

7. SOC Analyst Investigation Workflow

1. Monitor security events.
2. Identify the alert.
3. Investigate event details.
4. Check the source IP and username.
5. Understand the reason for the failure.
6. Classify the event.
7. Document the findings.

8. Learning Outcomes

Through this project, I learned:

- Basic Linux SSH authentication.
- Wazuh dashboard navigation.
- Security event monitoring.
- Failed login investigation.
- Basic alert classification.
- SOC analyst investigation workflow.

9. Conclusion

Successfully detected and investigated a failed SSH login attempt using Wazuh SIEM.

This hands-on project provided practical experience with security monitoring and basic SOC analyst activities.

10. Future Improvements

- Detect SSH brute-force attacks.
- Investigate repeated failed login attempts.
- Monitor suspicious IP addresses.
- Configure security notifications.
- Monitor Windows security events.

---

Author: SOC Analyst Beginner
Project: Wazuh SSH Login Failure Detection
