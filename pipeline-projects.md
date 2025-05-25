## 🏗️ Key DevOps Projects & Achievements

### 🚀 Multi-Environment Setup with Isolated Databases

Designed a complete **CI/CD architecture** using Azure Pipelines for 4 environments: Dev, Test, Preprod, Production.

Each environment featured:
- Separate **branch** (e.g., `dev`, `test`, `preproduction`, `production`)
- Unique **subdomain** (e.g., `dev.example.com`)
- Dedicated **IIS Application Pool**
- Isolated **SQL Server database**

> ✅ Fully automated deployments triggered by branch events.

---

### 💻 .NET Core Web App Pipeline

- Built a full CI/CD pipeline in **Azure Pipelines**.
- Used **custom appsettings** per environment.
- Deployed to **Azure VMs** with environment-specific settings and isolated SQL databases.

---

## ⚛️ React Frontend Pipeline

- Implemented a complete CI/CD pipeline using **Azure DevOps** for a React Single Page Application.
- Deployed to **Azure VMs** with environment-specific settings.
- Configure environment variable key and value in pipeline.

---

## 🅰️ Angular Frontend Pipeline

- End-to-end CI/CD pipeline for Angular.
- Configured isolated environments and environment-specific settings.

---

### 🐍 ERP System (Python) CI/CD Pipeline

- Developed CI/CD for a Python-based ERP system on **Ubuntu Server**.

---

## 📱 Flutter Mobile CI/CD Pipeline

- Fully automated CI/CD pipeline for **Flutter** mobile applications.
- Key features:
  - Builds **APK** (Android) and **IPA** (iOS) on push/merge events.
  - Distributes builds using:
    - **Firebase** for Android testers.
    - **TestFlight** for iOS testers.
  - Sends notifications via **SendGrid** to testers after successful builds.