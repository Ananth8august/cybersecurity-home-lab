# cybersecurity-home-lab
Home lab practice documenting hands-on learning in cybersecurity tools.
I built a SOC homelab where Wazuh monitors a Windows endpoint, attacks are generated from Kali Linux, and alerts are detected and analysed.

## 1. Lab Environment Setup
![VMware Home](screenshots/VM-Home.png)
This screenshot shows the VMware Workstation home lab environment with three virtual machines:
- Windows 11 (monitored endpoint)
- Kali Linux (attacker machine)
- Wazuh SIEM server (VASWA)

## 2. Network Configuration
![Windows IP Configuration](screenshots/Windows-ipconfig.png)
The IP configuration of the Windows 11 endpoint was identified to determine the target system for network reconnaissance.

![Kali Linux IP Configuration](screenshots/kali-ip.png)
This screenshot shows the Kali Linux machine IP configuration, confirming it is on the same network as the Windows endpoint.

## 3. Network Reconnaissance from Kali Linux
![Ping Test](screenshots/ping.png)
An ICMP ping test was performed from Kali Linux to verify connectivity with the Windows 11 endpoint.

![Nmap Port Scan](screenshots/nmap-portscan.png)
Nmap was used to identify open TCP ports on the Windows 11 system.

![Nmap Service Scan](screenshots/nmap-service-scan.png)
Service and version detection was performed using Nmap to gather additional information about exposed services.

## 4. Wazuh (VASWA) SIEM Monitoring
![Wazuh Login](screenshots/wazuh-login.png)
Login interface for accessing the Wazuh SIEM dashboard.

![Agent Management](screenshots/agent-management.png)
Agent Management view confirming that the Windows 11 endpoint agent is active and communicating with the Wazuh server.

![Rule Description](screenshots/rule-description.png)
Discover view showing security events with human-readable rule descriptions generated from Windows logs.

![Configuration Assessment](screenshots/configuration-assessment.png)
Configuration assessment results showing the security posture and baseline compliance of the Windows endpoint.

![Explore Discover](screenshots/explore-discover.png)
Explore → Discover view used to analyse collected security events and logs.

## 5. Key Observation
Basic network reconnaissance activities, such as ping and Nmap scanning, did not trigger high-severity alerts in Wazuh. This is expected behaviour because Wazuh is a log-based SIEM and relies on operating system and application logs. Network scanning alone does not generate Windows security events unless additional logging or IDS components are enabled.
