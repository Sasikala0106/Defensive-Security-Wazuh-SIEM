# 🛡️ Security Monitoring and Threat Detection using Wazuh SIEM

A hands-on cybersecurity project focused on deploying and configuring a **Wazuh SIEM (Security Information and Event Management)** environment to perform centralized security monitoring, log analysis, and real-time threat detection.

---

## 🎬 Live Demo

> ▶️ [Click here to watch the demo video](./demo/wazuh_demo.mp4)

---

## 📄 Final Report

> 📝 [View Full Project Report](./report/Wazuh_SIEM_Final_Report.pdf)

---

## 📌 Project Overview

This project demonstrates the deployment of a fully functional Wazuh SIEM environment using virtual machines. The system collects and analyzes logs from multiple agents, detects suspicious activity, and visualizes security events through the Wazuh Dashboard.

### Key Objectives
- Deploy Wazuh Server, Indexer, and Dashboard on Ubuntu
- Register and monitor Windows and Ubuntu agents
- Detect real-time security events such as failed logins and suspicious activity
- Analyze and visualize logs through the Wazuh Dashboard

---

## 🛠️ Tools & Technologies

| Category | Tools |
|---|---|
| SIEM Platform | Wazuh (Server, Indexer, Dashboard, Agent) |
| Virtualization | VirtualBox |
| Operating Systems | Ubuntu 22.04 LTS, Windows 10 |
| Log Analysis | Wazuh Dashboard, OpenSearch |
| Monitoring | System logs, Authentication logs, Security events |

---

## 🖥️ Lab Environment Setup

```
┌─────────────────────────────────────┐
│           VirtualBox Host           │
│                                     │
│  ┌──────────────────────────────┐   │
│  │  Ubuntu VM — Wazuh Server    │   │
│  │  + Indexer + Dashboard       │   │
│  └──────────────┬───────────────┘   │
│                 │                   │
│        ┌────────┴────────┐          │
│        ▼                 ▼          │
│  ┌───────────┐   ┌──────────────┐   │
│  │ Ubuntu VM │   │  Windows VM  │   │
│  │  Agent    │   │   Agent      │   │
│  └───────────┘   └──────────────┘   │
└─────────────────────────────────────┘
```

---

## ⚙️ Installation & Configuration

### 1. Install Wazuh Server (Ubuntu)
```bash
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh
sudo bash wazuh-install.sh -a
```

### 2. Access the Wazuh Dashboard
```
https://<wazuh-server-ip>
Default credentials: admin / <generated-password>
```

### 3. Register Ubuntu Agent
```bash
wget https://packages.wazuh.com/4.x/apt/pool/main/w/wazuh-agent/wazuh-agent_4.7.0-1_amd64.deb
sudo WAZUH_MANAGER='<wazuh-server-ip>' dpkg -i wazuh-agent_4.7.0-1_amd64.deb
sudo systemctl start wazuh-agent
```

### 4. Register Windows Agent
- Download the Wazuh Agent MSI installer from the Wazuh Dashboard
- Run the installer and enter the Wazuh Server IP
- Start the agent service from Windows Services

---

## 🔍 Key Features Demonstrated

- ✅ Centralized log collection from Ubuntu and Windows agents
- ✅ Real-time detection of failed SSH/RDP login attempts
- ✅ Alert generation and rule-based threat detection
- ✅ Security event visualization on the Wazuh Dashboard
- ✅ Authentication log analysis
- ✅ Suspicious activity monitoring and alerting

---

## 📸 Screenshots

> *(Add your dashboard screenshots here)*

| Dashboard Overview | Alert Detection | Agent Status |
|---|---|---|
| ![dashboard](./screenshots/dashboard.png) | ![alerts](./screenshots/alerts.png) | ![agents](./screenshots/agents.png) |

---




## 📚 References

- [Wazuh Official Documentation](https://documentation.wazuh.com)
- [Wazuh Installation Guide](https://documentation.wazuh.com/current/installation-guide/index.html)
