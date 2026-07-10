
# Wazuh Deployment

## Overview

This document describes the deployment process of the **Wazuh SIEM Platform** used in the project **Enhancing Wazuh SIEM with Cross-Layer Security and AI-Based Anomaly Detection**.

The deployment was performed using the official **Wazuh Quickstart Installation Script**, which automatically installs and configures the major Wazuh components, including the **Wazuh Manager**, **Wazuh Indexer**, and **Wazuh Dashboard** on a single Ubuntu server.

This deployment method provides a simple and efficient way to build a fully functional SIEM environment for security monitoring and log analysis.

---

# System Requirements

The deployment was performed on an Ubuntu Server with the following minimum specifications:

- Operating System: Ubuntu 22.04 LTS
- Processor: Dual-Core CPU or higher
- Memory: Minimum 4 GB RAM (8 GB Recommended)
- Storage: At least 50 GB available disk space
- Internet connection for downloading packages
- Sudo privileges

---

# Wazuh Quickstart Installation

The official Wazuh Quickstart installation script was used to install all required components.

Run the following command:

```bash
curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```

The installation process automatically downloads, installs, and configures the following components:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

No manual installation of individual components is required.

---

# Installed Components

## Wazuh Manager

The Wazuh Manager serves as the central component of the SIEM platform. It receives logs from all registered Wazuh Agents, analyzes security events using built-in decoders and rules, and generates rule-based alerts.

### Main Responsibilities

- Receive logs from Wazuh Agents
- Analyze security events
- Apply detection rules
- Generate alerts
- Forward processed logs to the Wazuh Indexer
- Provide raw logs to the AI Engine

---

## Wazuh Indexer

The Wazuh Indexer stores all processed security events received from the Wazuh Manager. It indexes the data to enable fast searching, filtering, and historical analysis.

### Main Responsibilities

- Store security logs
- Index events
- Enable fast searching
- Support dashboard queries
- Maintain historical records

---

## Wazuh Dashboard

The Wazuh Dashboard provides a web-based interface for centralized security monitoring and visualization.

Through the dashboard, security analysts can:

- Monitor connected agents
- View security alerts
- Search collected logs
- Investigate incidents
- Analyze security events
- Monitor system health

---

# Accessing the Dashboard

After the installation is completed, the Wazuh Dashboard can be accessed through a web browser using the server's IP address.

```
https://<SERVER-IP>
```

Example:

```
https://192.168.1.100
```

Log in using the credentials generated during the installation process.

---

# Deployment Verification

After deployment, verify that all Wazuh services are running correctly.

The following components should be operational:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

Successful deployment can be verified by:

- Opening the Wazuh Dashboard
- Logging into the dashboard
- Confirming that all services are active
- Verifying communication between the Manager and Dashboard

---

# Deployment Workflow

The deployment process follows these steps:

1. Install Ubuntu Server.
2. Update the operating system.
3. Download the official Wazuh Quickstart installation script.
4. Execute the installation script.
5. Automatically install the Wazuh Manager, Wazuh Indexer, and Wazuh Dashboard.
6. Access the Wazuh Dashboard through a web browser.
7. Verify that all Wazuh services are running successfully.
8. Proceed with Wazuh Agent deployment for the Host, Network, and Cloud layers.

---

# Result

The successful deployment provides a centralized SIEM platform capable of collecting, processing, indexing, and visualizing security events from multiple environments. The deployed Wazuh infrastructure serves as the foundation for integrating the AI Engine and enabling intelligent anomaly detection across the Host, Network, and Cloud layers.
