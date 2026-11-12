<div align="center">

# Real Estate CRM — Subh Sankalp

**A production multi-township CRM for plots, receipts, EMIs, commission and leads.**

[![Live](https://img.shields.io/badge/Live-platinumtownship.in-2ea44f?style=flat-square)](https://www.platinumtownship.in)
![.NET 8](https://img.shields.io/badge/.NET_8-512BD4?style=flat-square&logo=dotnet&logoColor=white)
![React](https://img.shields.io/badge/React_18-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![SQL Server](https://img.shields.io/badge/MS_SQL_Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)

</div>

> This repository is a public case study. The CRM's source code is private because it is a live company system; the README describes what it does and how it is built.

## Overview

Sales and accounts staff at Subh Sankalp Pvt Ltd use this CRM every day to book plots, cut receipts, track EMIs, pay associate commission and work leads. It runs **4 townships** with **970+ plots** and **2,600+ receipts**.

Three separate township CRMs were merged into this one system. During the migration, **₹60+ crore** of receipts were reconciled to the rupee.

## What it does

| Area | Details |
|---|---|
| **Plots** | Inventory with size, rate, PLC and status (Available, Tokened, Part Payment, Booked, Sold); bulk import |
| **Receipts** | Token, part-payment, booking, EMI and NOC receipts, numbered per township and printed as PDF on the township's letterhead |
| **EMI** | EMI plans and schedules, paid vs pending, EMI receipts |
| **Commission** | Commission per associate from the receipts they bring in, with payout records and proof |
| **Leads** | Website and Meta (Facebook) leads land in the CRM and are shared out to associates automatically |
| **Customers** | Customer login to see their own plot, receipts and dues |
| **Audit** | Every change recorded: who changed what, and when |
| **Mobile** | Android app built from the same React code with Capacitor, with Firebase push notifications |

## Engineering highlights

- **Multi-township data scoping**: every query is limited to the townships a user may open; admins can be company-wide or per township; one township can be private.
- **Background workers** (.NET hosted services):
  - token expiry: frees the plot and puts back its own price
  - lead distribution to associates
  - site-visit status
  - one-way sync from two legacy portals (inserts, edits and deletes)
- **OCR auto-fill**: Tesseract.js reads an Aadhaar or PAN photo in the browser and fills the receipt form.
- **Money rules enforced in the API**: zero, negative and over-payment receipts are refused, and plot status follows the paid percentage.
- **Safe production changes**: schema changes are applied by hand and recorded before code ships; data fixes run in one transaction with a backup table and checks.

## Architecture

```
React 18 + Vite + Tailwind  ──►  Azure Static Web Apps
Android app (Capacitor)             │
                                    │ HTTPS, JWT
                                    ▼
ASP.NET Core Web API (.NET 8) ──►  Azure App Service
  EF Core · Swagger · BCrypt        │
  hosted background workers         ├──►  Azure SQL (MS SQL Server)
                                    ├──►  Azure Blob Storage
                                    └──►  Firebase Cloud Messaging
Township websites ──► public plot and lead endpoints
```

## Tech stack

- **Backend:** C#, .NET 8, ASP.NET Core Web API, Entity Framework Core, JWT, BCrypt, Swagger/OpenAPI
- **Frontend:** React 18, Vite, Tailwind CSS, TanStack Query, React Hook Form, Recharts, Tesseract.js
- **Cloud and delivery:** Azure App Service, Azure Static Web Apps, Azure SQL, Azure Blob Storage, GitHub Actions, Firebase

## API sample

```http
POST /api/Auth/login                       staff sign-in, returns a JWT
POST /api/Auth/customer-login              customer portal sign-in
GET  /api/Plots/{id}                       one plot with paid %, balance and stage
PUT  /api/Plots/{id}                       edit a plot (customer price or new list price)
POST /api/Receipts/{id}/approve            approve a receipt
GET  /api/Receipts/{id}/emi-pdf            EMI receipt as PDF
POST /api/Receipts/process-expired-tokens  run token expiry now
GET  /api/EMI/schedule                     EMI schedule
GET  /api/Dashboard/stats                  dashboard figures
GET  /api/public/plots/summary             plot availability for the websites
POST /api/public/leads/ingest              website enquiry into the CRM
```

## Author

**Yogesh Garg**, Full Stack Developer at Subh Sankalp Pvt Ltd

[LinkedIn](https://www.linkedin.com/in/yogesh-garg-980517232) · [Portfolio](https://yogesh-portfolio-omega-seven.vercel.app) · [GitHub](https://github.com/yogugargoo7)
