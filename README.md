# soc-detection-lab
Hands-on SOC Home Lab for security monitoring, threat detection, log analysis, and incident investigation using Wazuh, Windows, Sysmon, and MITRE ATT&amp;CK.

🛡️ SOC Home Lab – Wazuh SIEM Deployment & Threat Monitoring
 Project Overview:

This project demonstrates the deployment of a Wazuh SIEM home lab on an Acer PC and Windows environment for centralized endpoint monitoring and security event analysis.

The lab was implemented to monitor endpoint logs, detect authentication failures, analyze security events, and map detected activities to the MITRE ATT&CK Framework through the Wazuh Dashboard.

Key Objectives:
Centralized endpoint log monitoring
Authentication failure detection
Security event analysis
MITRE ATT&CK mapping
Threat hunting and dashboard analysis
Investigation of endpoint security events

🖥️ Environment Setup
Component	Details
SIEM	Wazuh
Wazuh Version	4.14.6
Host Machine	Acer PC
Wazuh Manager	10.163.225.136
Linux Endpoint	192.168.100.5
Windows Endpoint	Windows 10
Linux Agent	Wazuh Agent
Monitoring	Wazuh Dashboard
Threat Framework	MITRE ATT&CK
⚙️ Wazuh Linux Agent Installation

The Wazuh agent was installed on the Linux endpoint and configured to communicate with the central Wazuh Manager.

Installation
sudo WAZUH_MANAGER="10.163.225.136" dpkg -i wazuh-agent_4.14.6-1_amd64.deb
Reload System Services
sudo systemctl daemon-reload
Enable Wazuh Agent
sudo systemctl enable wazuh-agent
Start Wazuh Agent
sudo systemctl start wazuh-agent

The agent was successfully installed and started, enabling communication with the central Wazuh Manager.

🔍 Detection & Monitoring Workflow
Endpoint Activity
       │
       ▼
Operating System Logs
       │
       ▼
Wazuh Agent
       │
       ▼
Wazuh Manager
       │
       ▼
Log Parsing & Detection
       │
       ▼
Security Alert
       │
       ▼
MITRE ATT&CK Mapping
       │
       ▼
Wazuh Dashboard
       │
       ▼
Threat Hunting & Analysis
📸 Lab Screenshots & Evidence
1. Linux Agent Installation & Status

The Wazuh agent was successfully installed and its running status was verified on the Linux Acer PC.

The screenshot demonstrates the active Wazuh agent service and its communication with the central Wazuh Manager.

Evidence




🚨 2. Wazuh Discover / Authentication Failure Logs

Wazuh Discover was used to analyze authentication-related system logs.

The captured PAM and unix_chkpwd logs show explicit failed password attempts.

Detection Details
Parameter	Value
Rule ID	5557
Severity Level	5
Log Sources	PAM / unix_chkpwd
Event Type	Authentication Failure

These logs demonstrate how raw operating system events are collected and analyzed as structured security events within Wazuh.

Evidence




🎯 3. MITRE ATT&CK Dashboard Analysis

The Wazuh Dashboard provides MITRE ATT&CK mapping for detected security events.

The authentication-related activity observed in this lab was categorized under:

MITRE Attribute	Details
Tactic	Credential Access
Technique	T1110.001
Technique Name	Password Guessing

This demonstrates the use of MITRE ATT&CK to provide context to detected security events.

Evidence







📊 4. Threat Hunting Summary & Analytics

The Wazuh dashboard was used to review overall security monitoring information, including:

Total alert metrics
Agent distribution
Authentication failure frequency
Security event activity
Overall endpoint security monitoring

This dashboard provides a centralized view for analyzing security events and monitoring endpoint security posture.

Evidence







🧩 MITRE ATT&CK Mapping

The detected authentication-related activity was mapped to the following MITRE ATT&CK technique:

Tactic	Technique	ID	Activity
Credential Access	Password Guessing	T1110.001	Failed authentication / password attempts
🔎 Key Findings

The lab successfully demonstrated:

Successful deployment of the Wazuh SIEM environment.
Successful installation and activation of the Linux Wazuh agent.
Centralized collection and analysis of endpoint logs.
Detection of authentication failures through PAM and unix_chkpwd logs.
Identification of Wazuh Rule ID 5557 with Severity Level 5.
Mapping of authentication-related activity to MITRE ATT&CK T1110.001 – Password Guessing.
Use of the Wazuh Dashboard for security monitoring and threat hunting analysis.
🛠️ Technologies Used
Wazuh SIEM
Linux
Windows 10
Wazuh Agent
Wazuh Manager
Wazuh Dashboard
MITRE ATT&CK
PAM
unix_chkpwd
