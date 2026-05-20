# 🛡️ Security Monitoring and Threat Detection using Wazuh SIEM

A hands-on cybersecurity project focused on deploying and configuring a **Wazuh SIEM (Security Information and Event Management)** environment to perform centralized security monitoring, log analysis, and real-time threat detection.

---

## 🎬 Live Demo

[![Wazuh SIEM Demo](https://img.youtube.com/vi/cwtTkdEac_Q/0.jpg)](https://youtu.be/cwtTkdEac_Q)

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


Wazuh Dashboard <img width="1600" height="840" alt="Wazuh Dashboard" src="https://github.com/user-attachments/assets/89f8c827-6000-45de-bda5-06c1d7baa227" />
Alerts <img width="1600" height="701" alt="Wazuh Alerts" src="https://github.com/user-attachments/assets/d54e2b2c-a807-4527-b277-8f98bd6eed77" /><br><br>
Authentication Logs <img width="612" height="352" alt="image" src="https://github.com/user-attachments/assets/83af868d-e1ca-4297-8359-f93d41399b5d"/> <img width="523" height="299" alt="image" src="https://github.com/user-attachments/assets/9ee678f3-4ed7-48ec-947c-4eb0372750a2"/> <img width="604" height="329" alt="image" src="https://github.com/user-attachments/assets/01023929-2e2b-42c5-bac5-a9ec337cf861" /><br>
File Intergrity Monitoring <img width="933" height="495" alt="image" src="https://github.com/user-attachments/assets/fb01cdec-529e-4d70-9cc8-7438885f8a31" />




---




## 📚 References

- [Wazuh Official Documentation](https://documentation.wazuh.com)
- [Wazuh Installation Guide](https://documentation.wazuh.com/current/installation-guide/index.html)
