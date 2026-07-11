# Enhancing Wazuh SIEM with Cross-Layer Security and AI-Based Anomaly Detection

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Wazuh](https://img.shields.io/badge/Wazuh-4.14-green)
![Machine Learning](https://img.shields.io/badge/Machine-Learning-orange)
![License](https://img.shields.io/badge/License-MIT-red)

---

## Overview

**Enhancing Wazuh SIEM with Cross-Layer Security and AI-Based Anomaly Detection** is a Final Year Project (FYP) that enhances the capabilities of the **Wazuh Security Information and Event Management (SIEM)** platform by integrating **Machine Learning** for intelligent anomaly detection.

Traditional SIEM systems primarily rely on predefined rules and signatures to identify cyber threats. While effective for detecting known attacks, these approaches may struggle to identify previously unseen or sophisticated attacks. This project addresses this limitation by integrating AI-based anomaly detection with Wazuh to improve security monitoring across multiple environments.

The proposed system collects security logs from **Host**, **Network**, and **Cloud** environments, processes them using Wazuh, analyzes them using trained machine learning models, and visualizes both rule-based and AI-generated alerts through the Wazuh Dashboard.

---

# Project Objectives

The objectives of this project are:

- Deploy a centralized Wazuh SIEM platform.
- Monitor Host, Network, and Cloud environments.
- Collect security logs from multiple sources.
- Integrate Machine Learning with Wazuh.
- Detect anomalous activities using AI models.
- Generate intelligent security alerts.
- Display AI-generated alerts on the Wazuh Dashboard.
- Improve threat detection accuracy across multiple security layers.

---

# Key Features

- Centralized SIEM platform using Wazuh
- Cross-layer security monitoring
- Host monitoring using Wazuh Agents
- Network security monitoring
- Cloud security monitoring
- AI-based anomaly detection
- Rule-based alert generation
- Machine Learning integration
- Real-time dashboard visualization
- Unified security monitoring platform

---

# System Architecture

The proposed architecture consists of:

- Host Layer
- Network Layer
- Cloud Layer
- Wazuh Agents
- Wazuh Manager
- Wazuh Indexer
- AI Engine
- Wazuh Dashboard

The complete architecture and workflow are available in:

📄 **[Architecture Documentation](Architecture/README.md)**

---

# Repository Structure

```
.
├── Architecture/
│   ├── Architecture.jpeg
│   └── README.md
│
├── Screenshots/
│   ├── Logs disply dashboard.jpeg
│   ├── connected devices.jpeg
│   ├── logs picture.jpeg
│   └── README.md
│
├── VIDEO/
│   └── README.md
│
├── datasets/
│   └── README.md
│
├── docs/
│   ├── AI-engine.md
│   ├── Agent-configuration.md
│   ├── installation.md
│   ├── wazuh-deployment.md
│   ├── dashboard.md
│   └── README.md
│
├── inference/
│   ├── ai_enriched.json
│   ├── ai_to_wazuh.ipynb
│   ├── fusion_engine.ipynb
│   ├── fusion_runtime.ipynb
│   ├── main_pipeline.ipynb
│   ├── wazuh_ai_fusion_pipeline_cells.ipynb
│   └── README.md
│
├── models/
│   ├── host_final.pkl
│   ├── cloud_rf_final.pkl
│   ├── dos_ddos_scaler.pkl
│   └── README.md
│
├── presentation/
│   └── final ppt of fyp.pptx
│
├── thesis/
│   ├── Updated Thesis 7.6.26.docx
│   └── README.md
│
├── training/
│   ├── Host.ipynb
│   ├── network.ipynb
│   ├── cloud.ipynb
│   ├── test.ipynb
│   └── README.md
│
└── README.md
```

---

# Technologies Used

| Category | Technology |
|-----------|------------|
| SIEM | Wazuh |
| Dashboard | Wazuh Dashboard |
| Search Engine | Wazuh Indexer |
| Machine Learning | Scikit-learn |
| Programming Language | Python |
| Virtualization | VMware Workstation |
| Cloud Platform | OpenStack |
| IDS | Suricata |
| Operating System | Ubuntu 22.04 LTS |

---

# Machine Learning Models

The AI Engine uses different machine learning models for different security layers.

| Security Layer | Machine Learning Model |
|---------------|------------------------|
| Host Layer | Isolation Forest |
| Network Layer | Random Forest |
| Cloud Layer | Random Forest |

The AI Engine analyzes security logs, detects anomalous behavior, and generates intelligent alerts that are integrated into the Wazuh SIEM platform.

---

# Deployment Environment

| Component | Deployment Environment |
|-----------|------------------------|
| Wazuh Server | Ubuntu 22.04 LTS (VMware Virtual Machine) |
| Host Layer | Linux Virtual Machine |
| Network Layer | Linux Virtual Machine |
| Cloud Layer | OpenStack Virtual Machine |
| AI Engine | Windows Host Machine |

---

# Installation

Detailed installation instructions are available in:

- 📄 [Installation Guide](docs/installation.md)
- 📄 [Wazuh Deployment](docs/wazuh-deployment.md)
- 📄 [Agent Configuration](docs/Agent-configuration.md)
- 📄 [AI Engine](docs/AI-engine.md)
- 📄 [Dashboard](docs/dashboard.md)

The project uses the official Wazuh Quick Start installation.

```bash
curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```

To install the Wazuh Agent on monitored endpoints:

```bash
sudo apt update
sudo apt install wazuh-agent
```

---

# Documentation

The project documentation is available inside the **docs** directory.

| File | Description |
|------|-------------|
| installation.md | Environment setup and software installation |
| wazuh-deployment.md | Wazuh deployment guide |
| Agent-configuration.md | Wazuh Agent configuration |
| AI-engine.md | AI Engine workflow |
| dashboard.md | Dashboard explanation |

---

# Datasets

The AI models were trained using publicly available cybersecurity datasets.

| Layer | Dataset |
|--------|----------|
| Host | ADFA-IDS |
| Network | CICIDS2017 |
| Cloud | Cloud Intrusion Detection Dataset |

More information:

📄 **[Dataset Documentation](datasets/README.md)**

---

# AI Workflow

The AI Engine performs the following tasks:

- Receive raw logs from the Wazuh Manager.
- Preprocess collected security data.
- Extract machine learning features.
- Execute trained machine learning models.
- Detect anomalous behavior.
- Generate AI-based alerts.
- Send alerts back to the Wazuh Manager.
- Display AI-generated alerts through the Wazuh Dashboard.

---

# Screenshots

Project screenshots demonstrating:

- Connected Wazuh Agents
- Security Event Dashboard
- Log Analysis
- Threat Hunting

are available inside:

📄 **[Dashboard Screenshots](Screenshots/README.md)**

---

# Project Demonstration

A demonstration video of the complete implementation is included in the repository.

The video demonstrates:

- Wazuh deployment
- Wazuh Agent registration
- Host monitoring
- Network monitoring
- Cloud monitoring
- AI model execution
- AI alert generation
- Dashboard visualization

More information:

📄 **[Project Demonstration](VIDEO/README.md)**

---

# Training

The machine learning model training notebooks are available in the **training** folder.

Included notebooks:

- Host.ipynb
- network.ipynb
- cloud.ipynb
- test.ipynb

---

# Inference Pipeline

The AI inference notebooks are available in the **inference** folder.

The inference pipeline performs:

- Log preprocessing
- Feature extraction
- AI prediction
- Alert generation
- Integration with Wazuh

---

# Results

The proposed system successfully demonstrates:

- Centralized log collection
- Multi-layer security monitoring
- AI-based anomaly detection
- Rule-based and AI-generated alerts
- Dashboard visualization
- Host monitoring
- Network monitoring
- Cloud monitoring

---

# Future Improvements

Potential future enhancements include:

- Deep Learning models
- SOAR integration
- Threat Intelligence feeds
- Docker deployment
- Kubernetes monitoring
- Automated incident response
- Email and SMS notifications
- Real-time streaming analytics

---

# Author

**Muhammad Awais**

Bachelor of Science in Computer Science (BSCS)

National University of Technology (NUTECH)

---


# Acknowledgements

This project utilizes the following open-source technologies and publicly available datasets:

- Wazuh
- OpenStack
- Python
- Scikit-learn
- Canadian Institute for Cybersecurity (CIC)
- UNSW Canberra Cyber

---

⭐ **If you found this project helpful, consider giving it a Star on GitHub.**
