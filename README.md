# 💼 PowerApps Salary Management & Approval System

![Platform](https://img.shields.io/badge/Platform-Microsoft%20Power%20Platform-742774?style=flat-square&logo=microsoft)
![PowerApps](https://img.shields.io/badge/PowerApps-Canvas%20App-742774?style=flat-square)
![Automate](https://img.shields.io/badge/Power%20Automate-Workflow-0066FF?style=flat-square)
![SharePoint](https://img.shields.io/badge/SharePoint-Data%20Storage-0078D4?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

> A cloud-based Employee Salary Management and Approval System built on Microsoft Power Platform — automating payroll requests, leave-based deductions, and manager approval workflows without traditional backend programming.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Technologies Used](#-technologies-used)
- [Features](#-features)
- [System Workflow](#-system-workflow)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [SharePoint Setup](#-sharepoint-setup)
- [Future Improvements](#-future-improvements)
- [Author](#-author)

---

## 🌐 Overview

The **PowerApps Salary Management & Approval System** is a fully cloud-based solution designed to streamline payroll operations within an organization. Built entirely on the **Microsoft Power Platform**, the system eliminates the need for manual salary processing by automating the entire lifecycle — from employee request submission to final approval and document generation.

Key capabilities include:
- Employees submit salary requests via an intuitive Power Apps canvas interface
- Leave days are automatically factored into deduction calculations
- Managers receive email notifications and can approve or reject requests in one click
- Upon approval, a formal salary letter is generated and delivered automatically

---

## 🛠 Technologies Used

| Technology | Role |
|---|---|
| **Microsoft Power Apps** (Canvas App) | User interface & form submission |
| **Microsoft Power Automate** | Workflow automation & approval logic |
| **SharePoint Online** | Cloud data storage & list management |
| **Microsoft Outlook** | Email notifications to employees & managers |
| **Microsoft Word Online** | Automated approval document generation |
| **OneDrive for Business** | Document storage & retrieval |
| **Power Platform CLI** | Source control conversion |
| **GitHub** | Version control |

---

## ✨ Features

- 📝 **Salary Request Submission** — Employees submit requests directly from the Power Apps UI
- 📉 **Leave-Based Deduction Calculation** — Automatically computes salary deductions based on leave days
- 💰 **Payable Salary Computation** — Net payable salary calculated in real time
- ✅ **Manager Approval / Rejection Workflow** — Structured approval flow with one-click actions
- 📧 **Email Notifications** — Automated emails sent to both managers and employees at each stage
- 📄 **Approval Document Generation** — Formal salary approval letter generated as a Word document
- ☁️ **Cloud Data Storage** — All data securely stored in SharePoint Online
- ⚡ **Full Workflow Automation** — End-to-end automation via Power Automate

---

## 🔄 System Workflow

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│  1. Employee submits salary request via Power Apps              │
│                         │                                       │
│                         ▼                                       │
│  2. Request stored in SharePoint list                           │
│                         │                                       │
│                         ▼                                       │
│  3. Power Automate triggers approval flow                       │
│                         │                                       │
│                         ▼                                       │
│  4. Manager receives approval request via email                 │
│                         │                                       │
│             ┌───────────┴───────────┐                           │
│             ▼                       ▼                           │
│         Approved               Rejected                         │
│             │                       │                           │
│             ▼                       ▼                           │
│  5. SharePoint status updated   Status updated to Rejected      │
│             │                                                   │
│             ▼                                                   │
│  6. Word approval letter generated                              │
│             │                                                   │
│             ▼                                                   │
│  7. Document saved to OneDrive                                  │
│             │                                                   │
│             ▼                                                   │
│  8. Email with document sent to employee                        │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## 📁 Project Structure

```
PowerApps-Salary-Management/
│
├── CanvasApps/         # UI screens, controls, and Power Fx formulas
│
├── Workflows/          # Power Automate approval workflow logic
│
├── Entities/           # Table references and metadata used by the solution
│
└── Other/              # Connection references and environment configuration
```

---

## 🚀 Getting Started

### Prerequisites

- A Microsoft 365 account with Power Apps and Power Automate access
- SharePoint Online site with appropriate permissions
- [Power Platform CLI](https://learn.microsoft.com/en-us/power-platform/developer/cli/introduction) installed

### Import Steps

**1. Install Power Platform CLI**
```bash
pac install latest
```

**2. Import the solution into your Power Apps environment**

Navigate to [make.powerapps.com](https://make.powerapps.com) → **Solutions** → **Import Solution**, then upload the `.zip` file from this repository.

**3. Reconnect data sources**

After import, reconnect the following:
- SharePoint Online list connection
- Microsoft Outlook connection

**4. Update connection references**

In the solution, update all connection references to point to your environment's SharePoint site and Outlook account.

**5. Publish the app**

Once connections are configured, publish the Canvas App to make it available to your users.

---

## 🗃 SharePoint Setup

Create a SharePoint list named **`SalaryRequests`** with the following columns:

| Column Name | Type | Description |
|---|---|---|
| `EmployeeName` | Single line of text | Full name of the employee |
| `EmployeeID` | Single line of text | Unique employee identifier |
| `BasicSalary` | Number | Base salary amount |
| `LeaveDays` | Number | Number of leave days taken |
| `DeductionAmount` | Number | Calculated deduction based on leave |
| `PayableSalary` | Number | Final net payable salary |
| `Status` | Choice | `Pending` / `Approved` / `Rejected` |

> **Note:** Ensure the Power Apps and Power Automate connections have read/write permissions on this list.

---

## 🔮 Future Improvements

- [ ] **Role-Based Access Control** — Separate permissions for employees, managers, and finance
- [ ] **Dashboard & Analytics** — Visual salary trends and approval statistics
- [ ] **Monthly Salary Reports** — Automated periodic report generation
- [ ] **Dataverse Integration** — Migrate from SharePoint to Microsoft Dataverse for enhanced scalability and security

---

## 👤 Author

**Rinesh Chaulagai**
B.Tech — Computer Science Engineering

---

> This project demonstrates how Microsoft Power Platform can be used to fully automate business processes — payroll approval, document generation, and employee management — without writing traditional backend code.
