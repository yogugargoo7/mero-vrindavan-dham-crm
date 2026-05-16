<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,6,30&height=180&section=header&text=Mero%20Vrindavan%20Dham&fontSize=36&fontColor=fff&animation=twinkling&fontAlignY=38&desc=Production-Ready%20Real%20Estate%20CRM%20%26%20Marketing%20Platform&descAlignY=58&descSize=15" width="100%"/>

[![.NET Core](https://img.shields.io/badge/.NET_Core-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/)
[![React](https://img.shields.io/badge/React.js-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![Azure](https://img.shields.io/badge/Microsoft_Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)](https://azure.microsoft.com/)
[![MS SQL Server](https://img.shields.io/badge/MS_SQL_Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)]()
[![GitHub Actions](https://img.shields.io/badge/CI%2FCD-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)]()

![Status](https://img.shields.io/badge/Status-Production%20Live-brightgreen?style=flat-square)
![Auth](https://img.shields.io/badge/Auth-JWT%20%2B%20Role--Based-blue?style=flat-square)
![API](https://img.shields.io/badge/API-Swagger%20Documented-85EA2D?style=flat-square)
![Cloud](https://img.shields.io/badge/Cloud-Azure%20App%20Service-0078D4?style=flat-square)

</div>

---

## 🏢 About

**Mero Vrindavan Dham** is a **production-deployed real estate CRM and marketing platform** built for Subh Sankalp Pvt Ltd. The system manages the complete lifecycle of real estate plots — from customer acquisition to booking, EMI tracking, and receipt generation.

> ⚡ *This is not a demo — it's a live business system handling real transactions.*

---

## 🌟 Key Highlights

| Feature | Details |
|---|---|
| 🔐 **Authentication** | JWT-based with role-based access control |
| 👥 **User Roles** | Admin · Associate · Customer |
| 🏗️ **Backend** | .NET Core Web API with Entity Framework Core |
| ⚛️ **Frontend** | React.js + Vite + Tailwind CSS |
| ☁️ **Cloud** | Azure App Service + Azure Blob Storage |
| 🔄 **CI/CD** | Automated GitHub Actions deployment pipeline |
| 📄 **API Docs** | Full Swagger / OpenAPI documentation |

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    CLIENT LAYER                         │
│   React.js + Vite + Tailwind CSS                        │
│   (Azure Static Web Apps)                               │
└─────────────────────┬───────────────────────────────────┘
                      │ HTTPS REST API
                      ▼
┌─────────────────────────────────────────────────────────┐
│                    API LAYER                            │
│   .NET Core Web API + ASP.NET Core                      │
│   JWT Authentication + Role-Based Authorization         │
│   Swagger / OpenAPI Documentation                       │
│   (Azure App Service)                                   │
└──────────┬──────────────────────┬───────────────────────┘
           │                      │
           ▼                      ▼
┌──────────────────┐   ┌──────────────────────────────────┐
│  DATABASE        │   │  CLOUD STORAGE                   │
│  MS SQL Server   │   │  Azure Blob Storage              │
│  Entity FW Core  │   │  (Documents, Media, Receipts)    │
└──────────────────┘   └──────────────────────────────────┘
```

---

## ✨ CRM Modules

### 🏡 Plot Management
- Full plot inventory with status tracking (Available / Booked / Sold)
- Bulk plot operations and category management
- Plot search and filtering

### 👤 Customer Management
- Customer registration and profile management
- Document upload via Azure Blob Storage
- Customer-plot relationship tracking

### 💰 EMI & Booking
- Flexible EMI plan configuration per plot
- EMI schedule generation and tracking
- Automated overdue alerts

### 🧾 Receipt Generation
- PDF receipt printing for payments
- Booking confirmation documents
- Transaction history

### 📊 Analytics Dashboard
- Sales performance metrics
- Revenue tracking and reporting
- Customer acquisition analytics

### 🌐 Marketing Website
- Lead capture chatbot integration
- Enquiry forms with CRM API integration
- WhatsApp flow for customer engagement

---

## 🛠️ Tech Stack

**Backend**
```
Language    : C# (.NET 8)
Framework   : ASP.NET Core Web API
Auth        : JWT Bearer Tokens + Role-Based Authorization
ORM         : Entity Framework Core
Docs        : Swagger / OpenAPI
```

**Frontend**
```
Framework   : React.js 18
Build Tool  : Vite
Styling     : Tailwind CSS
Features    : CRUD Screens, PDF Printing, Admin Dashboard
```

**Cloud & DevOps**
```
Hosting     : Azure App Service (API) + Azure Static Web Apps (UI)
Storage     : Azure Blob Storage (Documents & Media)
CI/CD       : GitHub Actions (Auto-deploy on push)
Database    : MS SQL Server
```

---

## 🔐 API Endpoints (Sample)

```http
POST   /api/auth/login              # JWT Authentication
GET    /api/plots                   # List all plots
POST   /api/plots                   # Create new plot
PUT    /api/plots/{id}/book         # Book a plot
GET    /api/customers               # Customer list
POST   /api/emi/generate/{booking}  # Generate EMI schedule
GET    /api/receipts/{id}/pdf       # Download PDF receipt
GET    /api/analytics/dashboard     # Analytics summary
```

---

## 🚀 Deployment

```yaml
# CI/CD via GitHub Actions — auto deploys on push to main
- Backend  → Azure App Service
- Frontend → Azure Static Web Apps
- Files    → Azure Blob Storage
```

---

## 👨‍💻 Developer

**Yogesh Garg** — Full Stack Developer @ Subh Sankalp Pvt Ltd

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/yogesh-garg-dev)
[![Portfolio](https://img.shields.io/badge/Portfolio-FF5722?style=flat-square&logo=todoist&logoColor=white)](https://yogeshgarg.dev)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:yogugarg000@gmail.com)

> 💡 *Open to Full Stack / Backend opportunities. Let's connect!*

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,6,30&height=80&section=footer" width="100%"/>
