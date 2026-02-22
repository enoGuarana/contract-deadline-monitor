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
