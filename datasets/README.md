# Datasets

## Overview

This project uses publicly available benchmark cybersecurity datasets to train and evaluate the machine learning models for anomaly detection across the **Host**, **Network**, and **Cloud** layers. These datasets were selected because they are widely used in cybersecurity research and contain realistic attack scenarios for developing and testing intrusion detection systems.

> **Note:** The datasets are **not included** in this repository due to their large size and licensing restrictions. Please download them from the official sources provided below.

---

# 1. Network Layer Dataset

### CICIDS2017 (Canadian Institute for Cybersecurity)

The **CICIDS2017** dataset was used to train and evaluate the machine learning model for detecting network-based attacks. It contains both normal and malicious network traffic generated in a realistic enterprise environment.

### Features

- Realistic network traffic
- Benign and malicious network flows
- Multiple attack categories
- Well-labeled data for supervised learning

### Included Attack Types

- DDoS
- DoS
- Brute Force
- Port Scan
- Botnet
- Web Attacks
- Infiltration
- Heartbleed

**Official Dataset**

https://www.unb.ca/cic/datasets/ids-2017.html

---

# 2. Host Layer Dataset

### ADFA Intrusion Detection Dataset (ADFA-IDS)

The **ADFA-IDS** dataset was used for host-based anomaly detection. It contains Linux system call traces collected from both normal system activities and multiple attack scenarios.

### Features

- Linux system call traces
- Normal user activities
- Attack behavior
- Suitable for host-based intrusion detection

### Included Attack Types

- Password Guessing
- Meterpreter
- Hydra FTP Attack
- Add User Attack
- Java Meterpreter
- Linux Exploits

**Official Dataset**

https://research.unsw.edu.au/projects/adfa-ids-datasets

---

# 3. Cloud Layer Dataset

### Cloud Intrusion Detection Dataset

A publicly available cloud security dataset was used to evaluate anomaly detection within cloud environments. The dataset contains cloud-generated security events and attack scenarios suitable for machine learning-based intrusion detection.

### Features

- Cloud activity logs
- Virtual machine events
- Network activities
- Cloud attack scenarios
- Labeled security events

**Research Paper**

https://www.sciencedirect.com/science/article/pii/S1084804523001807

---

# Dataset Usage in This Project

The datasets were preprocessed before training the machine learning models. The preprocessing pipeline included:

- Data cleaning
- Handling missing values
- Feature extraction
- Feature selection
- Data normalization
- Label encoding
- Training and testing split

The processed datasets were then used to train different machine learning models for each security layer.

| Security Layer | Dataset | Machine Learning Model |
|---------------|---------|------------------------|
| Host Layer | ADFA-IDS | Isolation Forest |
| Network Layer | CICIDS2017 | Random Forest |
| Cloud Layer | Cloud Intrusion Detection Dataset | Random Forest |

---

# Disclaimer

This repository does **not** redistribute the original datasets. All datasets remain the property of their respective authors and organizations. Please download them directly from the official sources listed above and follow their respective licensing and usage policies.
