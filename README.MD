# 🚨 Contract Deadline Monitor

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Azure](https://img.shields.io/badge/Azure-Functions-0078D4.svg)](https://azure.microsoft.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Status:** In Development (PoC)  
> **Context:** Ministry of Transport - CGIN/SGETI (Brazil)

## 📖 About the Project

Automated system for monitoring critical deadlines in concession contracts and additive terms. The solution aims to mitigate risks of inadvertent expiration by sending proactive alerts to responsible teams and providing managerial visibility via dashboard.

Aligned with **PDTIC 2024-2026** (ICT Governance) and the strategic objective of **Efficiency in Contractual Management**.

## 🚀 Features

- ✅ **Automated Ingestion**: Data reading via SharePoint/Excel.
- ✅ **Smart Alerts**: Notifications via Email/Teams (30, 15, and 7 days before expiration).
- ✅ **Audit Log**: Historical record of all sent notifications.
- ✅ **Managerial Dashboard**: Deadline visualization in Power BI.

## 🏗️ Architecture

```mermaid
graph LR
    A[SharePoint/Excel] -->|Data| B(Azure Function/Script)
    B -->|Logic| C{Check Deadlines}
    C -->|Yes| D[Send Alert Teams/Email]
    C -->|Yes| E[Log to SQL/Excel]
    B -->|Processed Data| F[Power BI]

🛠️ Technologies
Category
Technology
Language
Python 3.9+
Cloud
Azure (Functions, Logic Apps, Key Vault)
Data
SharePoint API, Excel
Visualization
Power BI
Control
Git/GitHub
⚙️ Installation and Setup
1. Prerequisites
Python 3.9 installed
Azure Account with appropriate permissions
Access to Ministry SharePoint/Lists
2. Environment Variables
Create a .env file in the root based on .env.example:
bash
12345
SHAREPOINT_SITE_URL=https://...
SHAREPOINT_LIST_NAME=Contracts
AZURE_TENANT_ID=...
EMAIL_SENDER=...
TEAMS_WEBHOOK_URL=...
3. Install Dependencies
bash
1
pip install -r requirements.txt
4. Run Locally
bash
1
python src/main.py
🔒 Security and Data Privacy (LGPD/GDPR)
Sensitive Data: This repository contains fictional data for portfolio purposes. In production, real data remains in the restricted Federal Government environment.
Secrets: No credentials are stored in the code. Use Azure Key Vault or environment variables.
Access: Alert access is restricted to managers responsible for each contract.
📊 Expected Results (KPIs)
100% Reduction in unmonitored expirations.
Estimated savings of X hours/month in manual verification.
Increased contractual compliance.
🤝 Contributing
This project is part of an internal initiative. For suggestions, contact the CGIN Data Team.
