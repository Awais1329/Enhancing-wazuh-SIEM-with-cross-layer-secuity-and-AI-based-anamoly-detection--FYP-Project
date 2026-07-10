# Installation Guide

## Overview

This document provides the complete installation guide for the **Enhancing Wazuh SIEM with Cross-Layer Security and AI-Based Anomaly Detection** project. The implementation consists of a centralized Wazuh SIEM platform deployed on an Ubuntu virtual machine, while the Host, Network, and Cloud environments are monitored using Wazuh Agents installed on separate virtual machines and devices.

The installation process includes preparing the virtual environment, installing the required software, setting up Python for the AI Engine, and installing Wazuh Agents on the monitored endpoints. Once the environment is prepared, the Wazuh platform can be deployed, and security monitoring can begin.

---

# Deployment Environment

The project was implemented using the following environment.

| Component | Deployment |
|-----------|------------|
| Wazuh Server | Ubuntu 22.04 LTS (VMware Virtual Machine) |
| Host Layer | Ubuntu/Kali Linux Virtual Machine |
| Network Layer | Linux Virtual Machine |
| Cloud Layer | OpenStack Virtual Machine |
| AI Engine | Windows Host Machine |

---

# Software Requirements

The following software was used throughout the implementation of the project.

- VMware Workstation
- Ubuntu 22.04 LTS
- Kali Linux
- OpenStack
- Python 3.x
- Wazuh 4.14
- Suricata IDS
- Git

---

# Preparing the Operating System

Before installing any software, update the operating system to ensure all packages are current.

```bash
sudo apt update
sudo apt upgrade -y
```

---

# Installing Git

Git is required to clone repositories and manage project files.

```bash
sudo apt install git -y
```

Verify the installation.

```bash
git --version
```

---

# Installing Python

Python is required for the AI Engine and machine learning models.

Install Python using the following command.

```bash
sudo apt install python3 python3-pip -y
```

Verify the installation.

```bash
python3 --version
pip3 --version
```

---

# Installing Python Dependencies

The AI Engine requires several Python libraries for preprocessing, machine learning, and data analysis.

Install the required libraries using:

```bash
pip install pandas numpy scikit-learn matplotlib joblib notebook
```

These libraries are used for:

- Data preprocessing
- Feature engineering
- Machine learning model execution
- Log analysis
- AI-based anomaly detection

---

# Installing Wazuh Agents

To enable centralized security monitoring, a Wazuh Agent must be installed on every monitored endpoint, including the **Host**, **Network**, and **Cloud** virtual machines.

First, update the package list.

```bash
sudo apt update
```

Install the Wazuh Agent.

```bash
sudo apt install wazuh-agent
```

After the installation is complete, the Wazuh Agent package is available on the endpoint. The agent can then be configured to communicate with the centralized Wazuh Manager. Once configured and started, it begins collecting operating system events, authentication logs, network activities, and other security-related information before securely forwarding the collected logs to the Wazuh Server for analysis.

The detailed agent configuration and registration process is explained in **Agent-Configuration.md**.

---

# Network Configuration

All virtual machines and monitored systems must be connected through the same network so they can communicate with the centralized Wazuh Server.

Before proceeding, verify that:

- The Wazuh Server is reachable from all monitored endpoints.
- Host Layer can communicate with the Wazuh Server.
- Network Layer can communicate with the Wazuh Server.
- Cloud Layer can communicate with the Wazuh Server.
- The AI Engine can communicate with the Wazuh Server.

Proper network connectivity is required for successful log collection and centralized monitoring.

---

# Installation Workflow

The installation process follows these steps:

1. Install VMware Workstation.
2. Create the required virtual machines.
3. Install Ubuntu 22.04 LTS for the Wazuh Server.
4. Install Ubuntu/Kali Linux virtual machines for the Host and Network layers.
5. Deploy the OpenStack virtual machine for the Cloud Layer.
6. Update all operating systems.
7. Install Git.
8. Install Python and the required machine learning libraries.
9. Install the Wazuh Agent on the Host, Network, and Cloud endpoints.
10. Verify network communication between all systems.
11. Continue with the Wazuh Server deployment.

---

# Next Step

After completing the installation of the required software and Wazuh Agents, proceed to **Wazuh-Deployment.md**, which explains how to deploy the Wazuh Manager, Wazuh Indexer, and Wazuh Dashboard using the official Wazuh Quickstart installation script.
