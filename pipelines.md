# 📘 Project Documentation Template

## 1. 📄 Project Overview

**Project Name**:  
**Owner/Team**:  
**Start Date**:  
**Status**: (In Progress / Live / Maintenance)  
**Primary Purpose**:  

**Main Tech Stack**:  
- **Backend**: (e.g., .NET Core, Node.js)  
- **Frontend**: (e.g., React, Flutter)  
- **Database**: (e.g., SQL Server, MongoDB)  
- **Hosting**: (e.g., Azure, AWS, On-Prem)  

---

## 2. 🔌 Integrations Overview

| Service    | Purpose                      | Integration Method       | Credentials Location         | Status     |
|------------|------------------------------|---------------------------|-------------------------------|------------|
| SendGrid   | Send Email/SMS Notifications | SMTP / REST API           | Azure Key Vault / Env Vars   | ✅ Active  |
| FTP Server | Image Upload and Sync        | FTP/SFTP Protocol         | Stored in Secrets Manager    | ✅ Active  |
| Firebase   | Real-Time Chat & Presence    | Firebase SDK / REST API   | Firebase Console              | ✅ Active  |
| Hangfire   | Background Job Scheduling     | Built-in Dashboard / API  | App Configuration             | ✅ Active  |

---

## 3. 🔧 Integration Details

### 3.1 SendGrid (Emails / SMS)

- **Use Case**: Send account confirmation, password reset, and marketing emails.  
- **SDK/Library**: SendGrid C# SDK v9.x  
- **Endpoint(s)**:  
  - `POST /api/notifications/email`  
- **Config Keys**:  
  - `SENDGRID_API_KEY`: stored in Azure Key Vault  
- **Environment**:  
  - Development: Disabled  
  - Production: Enabled  
- **Monitoring**:  
  - Logs via Application Insights  

---

### 3.2 FTP Server (Image Uploads)

- **Use Case**: Store and retrieve user-uploaded images.  
- **Protocol**: SFTP  
- **FTP Host**: `ftp.example.com`  
- **Credentials Location**: `/etc/secrets/ftp.env`  
- **Upload Path**: `/uploads/images/yyyy/MM/dd/`  
- **Security**:  
  - Encrypted channel (SFTP)  
  - IP Whitelisting  

---

### 3.3 Firebase (Real-Time Chat)

- **Use Case**: Enable real-time chat between users.  
- **Service**: Firebase Realtime Database  
- **Library**: Firebase JS SDK  
- **Main Features**:  
  - Message sync  
  - Online status tracking  
  - Push notifications  
- **Security Rules**: Configured in Firebase Console  
- **Backup Policy**: Daily via Firebase CLI  

---

### 3.4 Hangfire (Background Jobs)

- **Use Case**: Run scheduled and background tasks (e.g., email queues, data sync).  
- **Library**: Hangfire.Core 1.7.x  
- **Dashboard URL**: `/hangfire`  
- **Job Types**:  
  - Daily Reports  
  - Email Queue  
  - Cleanup Tasks  
- **Storage**: SQL Server  
- **Retries**: 3 retries on failure  
- **Monitoring**: Hangfire Dashboard & Email alerts  

---

## 4. 🔐 Secrets & Configuration

| Key Name           | Description              | Environment Variable | Source             |
|--------------------|--------------------------|----------------------|--------------------|
| SENDGRID_API_KEY   | SendGrid Auth Key        | ✅                   | Azure Key Vault    |
| FIREBASE_CONFIG    | Firebase API Config      | ✅                   | Env File           |
| FTP_CREDENTIALS    | FTP Server Auth          | ✅                   | Secret Manager     |
| HANGFIRE_CONN      | Hangfire DB Connection   | ✅                   | Config File        |

---

## 5. 📈 Monitoring & Logging

| Tool                  | Purpose                        | Dashboard URL                                | Alerts? |
|-----------------------|--------------------------------|----------------------------------------------|---------|
| Application Insights  | General logs & exceptions      | https://portal.azure.com                     | ✅       |
| Firebase Console      | Realtime DB Usage & Errors     | https://console.firebase.google.com          | ✅       |
| Hangfire Dashboard    | Job status & errors            | `/hangfire`                                  | ✅       |
| FTP Logs              | Upload/download audit          | `/var/log/ftp.log`                           | ❌       |

---

## 6. 🧪 Testing & Validation

| Integration | Test Method            | Notes                              |
|-------------|------------------------|------------------------------------|
| SendGrid    | SMTP Test via Postman  | Confirm email format and rate      |
| FTP         | File Upload Script     | Check file permissions             |
| Firebase    | Simulated Chat Session | Verify sync speed                  |
| Hangfire    | Trigger Test Jobs      | Watch logs and retry logic         |

---

## 7. 📦 Deployment Notes

- **Deployment Method**: Azure DevOps Pipeline / GitHub Actions  
- **Secrets Injection**: via Azure Key Vault binding  
- **Rollback Plan**: Redeploy previous commit from pipeline  
- **Environment Separation**: Each environment has its own config file and secrets  

---

## 8. 🧾 Change History

| Date       | Change Description                     | Author       |
|------------|-----------------------------------------|--------------|
| 2025-05-01 | Integrated Firebase Chat Module         | M. Bendary   |
| 2025-04-20 | Migrated FTP Server to SFTP             | M. Bendary   |
| 2025-03-15 | Set up Hangfire for background jobs     | M. Bendary   |

---
