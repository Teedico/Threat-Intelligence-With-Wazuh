# Threat-Intelligence-With-Wazuh

# Enhancing Threat Intelligence Feeds in SOC Operations  

## Project Overview  
Security Operations Centers (SOCs) rely on **threat intelligence feeds** to detect, hunt, and respond to cyber threats. However, the overwhelming volume of alerts can lead to **false positives** and analyst fatigue.  

This project integrates **VirusTotal** with **Wazuh (an open-source SIEM)** to enhance SOC operations by improving threat feed processing, optimizing alerts, and reducing noise. By leveraging VirusTotal’s vast database and Wazuh’s detection capabilities, SOC analysts can identify genuine threats faster and more effectively.  


## Objectives  
- Analyze and optimize the integration of threat intelligence feeds within **Wazuh**, using **VirusTotal**.  
- Streamline threat detection and reduce false positives in SOC operations.  
- Improve incident response by enriching alerts with **threat intelligence context**.  
- Demonstrate how small enhancements in threat processing can significantly strengthen SOC efficiency.  

## Skills Learned  
- Advanced understanding of **SIEM concepts** and **SOC workflows**.  
- Proficiency in **monitoring, analyzing, and interpreting alert logs**.  
- Developing **custom Wazuh rules** to query VirusTotal.  
- Integrating **threat intelligence APIs** into a SIEM.  
- Gathering and enriching **Indicators of Compromise (IOCs)**.  
- Applying **cybersecurity frameworks** for compliance.  
- Deploying endpoints to a **Cloud-based SIEM** (AWS EC2).  
- Navigating alerts and generating comprehensive SOC reports.  

## Tools & Technologies Used  
- **AWS (EC2 instance)** – Cloud infrastructure to host Wazuh.  
- **Wazuh** – SIEM platform for log analysis, rule creation, and threat monitoring.  
- **VirusTotal** – Threat intelligence API for file, URL, and IP reputation checks.  
- **Windows Endpoints** – To generate test alerts.  
- **Kali Linux** – Attack simulation and alert generation.  


## Implementation Steps  

### 1. Environment Setup  
- Launch an **EC2 instance** on AWS.  
- Connect to the instance and update the server:  
  ```bash
  sudo apt-get update && sudo apt-get upgrade
  ```  
- Install Wazuh:  
  ```bash
  curl -sO https://packages.wazuh.com/4.9/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
  ```  

### 2. VirusTotal API Integration  
- Create a **VirusTotal account** and generate an API key.  
- Edit the Wazuh configuration file:  
  ```bash
  sudo nano /var/ossec/etc/ossec.conf
  ```  
- Add the VirusTotal API key to enable integration.  
- Restart the Wazuh manager to apply changes.  
- Confirm the integration via the **Wazuh settings dashboard**.  

### 3. File Integrity Monitoring (FIM)  
- Enable **File Integrity Monitoring** in Wazuh to trigger VirusTotal queries on suspicious activity.  
- Configure rules so that when files, URLs, or IPs are detected, Wazuh automatically queries VirusTotal.  

### 4. Alert Monitoring & Analysis  
- Wazuh queries VirusTotal in real-time to classify events.  
- Malicious activity is flagged, reducing false positives.  
- SOC analysts can prioritize real alerts and respond efficiently.  

## Results & Findings  
- Reduced false positives by enriching alerts with VirusTotal intelligence.  
- Improved analyst efficiency with automated classification of files, IPs, and URLs.  
- Strengthened SOC operations through **real-time intelligence-driven detection**.  

## Conclusion  
This project highlights the **critical role of enriched threat intelligence feeds** in SOC operations.By integrating VirusTotal with Wazuh, Even small improvements in feed processing can:
- Reduce analyst workload through fewer false positives.  
- Improve detection accuracy by enriching alerts with reliable intelligence.  
- Strengthen proactive defense strategies.  

**For Future Work:**  
- Explore automation and machine learning to make threat intelligence adaptive.  
- Integrate additional threat intelligence sources to provide broader visibility and richer context. 
