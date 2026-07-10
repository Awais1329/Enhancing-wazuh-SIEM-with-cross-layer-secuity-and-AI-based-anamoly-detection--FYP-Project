
# Agent Configuration

## Overview

This document describes the deployment and configuration of the Wazuh Agents used in the proposed **Enhancing Wazuh SIEM with Cross-Layer Security and AI-Based Anomaly Detection** system.

To achieve centralized security monitoring, Wazuh Agents were deployed across three different security layers: **Host**, **Network**, and **Cloud**. Each agent continuously collects security events and system logs from its respective environment and securely forwards them to the centralized Wazuh Manager.

Unlike a traditional deployment where all components reside on a single machine, this project distributes the monitored environments across multiple virtual machines and physical devices. This architecture better simulates a real-world enterprise network, where different systems operate independently while reporting security events to a centralized SIEM platform.

---

# Deployment Environment

The complete implementation consists of multiple virtual machines and physical devices connected through the network.

| Component | Deployment Environment |
|-----------|------------------------|
| Wazuh Server | Ubuntu 22.04 LTS (VMware Virtual Machine) |
| Host Layer | Ubuntu/Kali Linux Virtual Machine |
| Network Layer | Separate Virtual Machine |
| Cloud Layer | OpenStack Virtual Machine |
| AI Engine | Windows Host Machine |

The Ubuntu virtual machine hosts the centralized Wazuh infrastructure, including the Wazuh Manager, Wazuh Indexer, and Wazuh Dashboard. The Host, Network, and Cloud environments are deployed independently and communicate with the Wazuh Manager through registered Wazuh Agents.

---

# Installing the Wazuh Agent

Each monitored system requires a Wazuh Agent to enable communication with the centralized Wazuh Server. The agent is responsible for collecting logs, monitoring endpoint activities, and securely forwarding security events to the Wazuh Manager.

The agent was installed using the Ubuntu package manager.

```bash
sudo apt update
sudo apt install wazuh-agent
```

After installation, the Wazuh Agent configuration file was updated with the IP address of the Wazuh Manager running on the Ubuntu server. The agent was then registered with the Wazuh Server and the service was started.

Once successfully connected, the monitored endpoint became visible in the Wazuh Dashboard, confirming successful communication between the agent and the manager.

---

# Host Layer Configuration

The Host Layer was deployed using a Linux virtual machine to simulate a monitored endpoint. A Wazuh Agent was installed on the system to continuously observe operating system activities and security events.

The Host Layer collects various types of endpoint data, including system logs, authentication events, user activities, running processes, and file integrity events. File Integrity Monitoring (FIM) continuously checks important system files and generates alerts whenever unauthorized modifications are detected.

The collected logs are securely transmitted to the Wazuh Manager, where they are decoded, analyzed, and correlated with predefined security rules. This allows the SIEM platform to detect suspicious endpoint behavior and generate security alerts in real time.

### Monitored Activities

- System Logs
- Authentication Logs
- User Login Events
- File Integrity Monitoring (FIM)
- Process Monitoring
- User Activity
- Operating System Events

---

# Network Layer Configuration

The Network Layer was deployed on a separate virtual machine responsible for monitoring network activities. A Wazuh Agent was installed to collect security events generated from the network monitoring environment.

This layer continuously monitors network-related events and forwards collected logs to the centralized Wazuh Manager. The Network Layer enables the detection of suspicious network activities such as abnormal connections, unauthorized communication attempts, and other security-related events.

In practical deployments, this layer can also integrate with network intrusion detection systems such as Suricata, allowing IDS alerts to be forwarded directly into the Wazuh SIEM platform for centralized analysis.

### Monitored Activities

- Network Events
- Connection Logs
- Traffic Monitoring
- Security Events
- IDS Alerts
- Network Activity Logs

---

# Cloud Layer Configuration

The Cloud Layer was implemented using an OpenStack virtual machine to simulate a cloud computing environment. A Wazuh Agent was installed inside the virtual machine to continuously monitor cloud infrastructure and operating system activities.

The Cloud Layer collects authentication logs, virtual machine events, system logs, and cloud service activities. These logs are securely transmitted to the centralized Wazuh Manager where they are analyzed together with logs received from the Host and Network layers.

This centralized monitoring approach provides complete visibility across hybrid environments consisting of physical systems, virtual machines, and cloud infrastructure.

### Monitored Activities

- Virtual Machine Events
- Cloud Authentication Logs
- System Logs
- Cloud Service Logs
- User Activities
- Security Events

---

# Communication with the Wazuh Manager

All deployed Wazuh Agents establish secure communication with the centralized Wazuh Manager hosted on the Ubuntu VMware virtual machine.

Once communication is established, every monitored endpoint periodically sends collected security events to the manager. The Wazuh Manager receives these events, decodes the incoming logs, normalizes the data, and applies built-in as well as custom security rules to identify suspicious activities.

After processing, the analyzed logs are forwarded to the Wazuh Indexer for storage while generated alerts become available through the Wazuh Dashboard.

This centralized communication architecture enables security analysts to monitor multiple environments from a single dashboard without directly accessing individual systems.

---

# AI Engine Integration

Unlike the monitored systems, the AI Engine was deployed on a Windows host machine instead of a virtual machine.

The AI Engine acts as an intelligent analysis layer that extends the capabilities of the traditional SIEM platform.

Raw logs collected by the Wazuh Manager are provided to the AI Engine for additional processing. Before analysis, the logs undergo preprocessing steps including data cleaning, feature extraction, normalization, and transformation into machine learning features.

The project uses trained machine learning models to analyze logs collected from different security layers:

- Isolation Forest for Host Layer anomaly detection
- Random Forest for Network Layer intrusion detection
- Random Forest for Cloud Layer anomaly detection

Once prediction is completed, the AI Engine determines whether an event represents normal behavior or a potential security threat. If suspicious activity is detected, an AI-generated alert is created and automatically forwarded back to the Wazuh Manager.

These AI-generated alerts are stored together with traditional rule-based alerts and become immediately visible through the Wazuh Dashboard, providing security analysts with enhanced threat detection capabilities.

---

# Deployment Summary

The final deployment demonstrates a centralized SIEM architecture capable of monitoring multiple environments simultaneously. Wazuh Agents deployed across the Host, Network, and Cloud layers continuously collect security logs and securely forward them to the Wazuh Manager. The manager performs rule-based analysis while simultaneously supplying raw logs to the AI Engine for machine learning-based anomaly detection.

The AI Engine enhances traditional SIEM capabilities by identifying suspicious behaviors that may not match predefined detection rules. Finally, both rule-based and AI-generated alerts are stored in the Wazuh Indexer and visualized through the Wazuh Dashboard, providing a unified platform for real-time security monitoring, incident investigation, and intelligent threat detection.
