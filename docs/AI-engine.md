
# AI Engine

## Overview

The AI Engine is a core component of the proposed **Enhancing Wazuh SIEM with Cross-Layer Security and AI-Based Anomaly Detection** system. It enhances the traditional rule-based detection capabilities of Wazuh by integrating machine learning models capable of identifying anomalous behavior and previously unseen cyber threats.

Unlike conventional SIEM systems that rely solely on predefined rules and signatures, the AI Engine performs intelligent analysis on security logs collected from the **Host**, **Network**, and **Cloud** layers. This enables the system to detect both known attacks and abnormal activities that may not match existing security rules.

The AI Engine was deployed on a **Windows host machine**, where it continuously receives security logs from the Wazuh Manager, processes them through a machine learning pipeline, and returns AI-generated alerts back to the Wazuh SIEM platform.

---

# AI Architecture

The AI Engine acts as an additional analysis layer between the Wazuh Manager and the Wazuh Dashboard.

The complete workflow consists of the following stages:

1. Security logs are collected from the Host, Network, and Cloud layers.
2. Wazuh Agents forward the logs to the Wazuh Manager.
3. The Wazuh Manager processes and stores the collected events.
4. Raw log data is provided to the AI Engine.
5. The AI Engine preprocesses and transforms the logs into machine learning features.
6. The trained machine learning models classify each event as normal or suspicious.
7. AI-generated alerts are created for detected anomalies.
8. These alerts are sent back to the Wazuh Manager.
9. The Wazuh Dashboard displays both rule-based and AI-generated alerts for centralized monitoring.

---

# Data Collection

The AI Engine receives security logs collected from three different environments.

## Host Layer

The Host Layer provides operating system and endpoint security logs, including:

- System Logs
- Authentication Logs
- File Integrity Monitoring (FIM)
- Process Execution Events
- User Activity Logs

---

## Network Layer

The Network Layer provides security events generated from network monitoring.

Collected data includes:

- Network Traffic Logs
- IDS Alerts
- Connection Events
- Network Security Logs

---

## Cloud Layer

The Cloud Layer provides logs collected from the OpenStack virtual machine.

These logs include:

- Cloud Authentication Logs
- Virtual Machine Events
- System Logs
- Cloud Service Logs

---

# Data Preprocessing

Before machine learning models analyze the collected logs, the AI Engine performs several preprocessing steps.

These include:

- Removing unnecessary information
- Handling missing values
- Encoding categorical features
- Feature extraction
- Feature normalization
- Preparing data for prediction

Preprocessing ensures that security logs are transformed into a format suitable for machine learning algorithms.

---

# Machine Learning Models

Different machine learning models were selected based on the characteristics of each security layer.

## Host Layer Model

The Host Layer uses the **Isolation Forest** algorithm.

Isolation Forest is an unsupervised anomaly detection model that isolates unusual observations instead of learning predefined attack signatures. It is well suited for identifying abnormal endpoint behavior without requiring labeled attack data.

### Purpose

- Detect abnormal system behavior
- Identify suspicious user activities
- Detect unknown host anomalies

---

## Network Layer Model

The Network Layer uses the **Random Forest** classifier.

Random Forest is a supervised machine learning algorithm trained using the CICIDS2017 dataset. It classifies network traffic into normal and malicious categories.

### Purpose

- Detect malicious network traffic
- Identify intrusion attempts
- Classify network attacks

---

## Cloud Layer Model

The Cloud Layer also uses a **Random Forest** classifier trained on a cloud intrusion detection dataset.

The model analyzes cloud security events and identifies abnormal activities occurring within virtualized environments.

### Purpose

- Detect cloud-based attacks
- Monitor virtual machine activities
- Identify suspicious cloud behavior

---

# Prediction Process

Once preprocessing is completed, the appropriate machine learning model is selected according to the source of the collected logs.

Each model analyzes the incoming security events and generates a prediction indicating whether the activity is normal or suspicious.

If suspicious behavior is detected, the AI Engine generates an alert containing relevant security information.

---

# AI Alert Generation

After prediction, the AI Engine creates structured security alerts containing:

- Alert Timestamp
- Security Layer
- Prediction Result
- Threat Classification
- Confidence Score (if available)
- Event Details

These alerts provide additional context beyond traditional rule-based detection.

---

# Integration with Wazuh

One of the key objectives of this project is integrating machine learning with the Wazuh SIEM platform.

After generating an AI alert, the AI Engine sends the alert back to the Wazuh Manager.

The Wazuh Manager processes the received AI alerts together with standard Wazuh alerts before forwarding them to the Wazuh Indexer.

Finally, the Wazuh Dashboard displays both types of alerts through a single centralized interface.

This integration allows security analysts to investigate rule-based detections and AI-generated anomalies from one dashboard.

---

# Advantages of the AI Engine

The AI Engine provides several improvements over traditional SIEM systems.

- Detects previously unseen attacks
- Identifies anomalous behavior
- Reduces dependence on predefined rules
- Improves threat detection accuracy
- Supports intelligent security monitoring
- Enhances incident investigation
- Complements traditional Wazuh rule-based detection

---

# AI Workflow Summary

The complete AI workflow can be summarized as follows:

1. Security logs are collected from the Host, Network, and Cloud layers.
2. Wazuh Agents forward the logs to the Wazuh Manager.
3. The Wazuh Manager provides raw log data to the AI Engine.
4. The AI Engine preprocesses the collected logs.
5. Machine learning models analyze the processed data.
6. Predictions are generated for each security event.
7. AI-generated alerts are created for suspicious activities.
8. Alerts are sent back to the Wazuh Manager.
9. The Wazuh Dashboard displays both rule-based and AI-generated alerts in real time.

---

# Summary

The AI Engine extends the capabilities of the Wazuh SIEM platform by integrating machine learning-based anomaly detection into the security monitoring workflow. By combining traditional rule-based analysis with intelligent predictive models, the proposed system provides more comprehensive threat detection across the Host, Network, and Cloud layers. This hybrid approach enables earlier identification of suspicious activities, improves detection accuracy, and supports more effective security monitoring through a centralized dashboard.
