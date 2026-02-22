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


---

## 🛡️ 3. Critical Security (Do Not Ignore!)

Since you are handling government data, **never** upload real information to a public GitHub.

1.  **`.gitignore` File**:
    Create this file in the root to ensure passwords and data are not accidentally pushed.
    ```gitignore
    .env
    __pycache__/
    *.pyc
    .vscode/
    real_data/*.xlsx
    notebooks/.ipynb_checkpoints
    ```

2.  **`.env.example` File**:
    Create an example file **without real values** so anyone downloading the repo knows what to configure.
    ```bash
    # .env.example
    SHAREPOINT_SITE_URL= https://your-tenant.sharepoint.com/sites/YourSite
    CLIENT_ID= your-client-id
    CLIENT_SECRET= your-secret
    ```

3.  **Dummy Data**:
    For the GitHub to be public (portfolio), create a spreadsheet `contracts_example.xlsx` with **fake data** (e.g., "Highway X Concession", "Expiration: 2099"). **Never** use real process numbers or real financial values.

4.  **Private vs. Public Repository**:
    *   **Private:** If you are using real ministry data (even if anonymized), keep the repo **Private**.
    *   **Public:** If you want to show this in your portfolio, use **only synthetic data** and make sure no internal URLs (e.g., `interno.transportes.gov.br`) are visible in the code.

5.  **License**:
    For government software in Brazil, **Creative Commons** or **MIT** are common. For a personal portfolio, **MIT** is standard and shows you understand open-source norms.

---

## 💡 4. Final Tips for Your Portfolio

1.  **Commit Messages**: Use standard conventions (e.g., [Conventional Commits](https://www.conventionalcommits.org/)).
    *   ✅ `feat: add teams notification logic`
    *   ✅ `fix: correct sharepoint connection timeout`
    *   ❌ `update code`
2.  **Issues & Projects**: Use GitHub Issues to track tasks (e.g., "Implement Email Alert", "Connect Power BI"). This shows you know how to manage projects.
3.  **Pin the Repo**: Once finished, pin this repository to your GitHub profile homepage.
4.  **Description**: In the repo "About" section (sidebar), write: *Automated contract deadline monitoring system using Python and Azure. Developed for the Brazilian Ministry of Transport.*

This structure shows **technical competence**, **security awareness**, and **professionalism**—key traits for both public sector roles and private tech companies.

Would you like help writing the **Python code** for the `connectors.py` or `notifier.py` modules next? 🚀
