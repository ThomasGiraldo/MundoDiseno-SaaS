# MundoDiseno-SaaS
Inventory management platform and web catalog for the construction sector
# Mundo Diseño — Inventory Panel & Web Catalog (SaaS)

![Next JS](https://img.shields.io/badge/Next-black?style=for-the-badge&logo=next.js&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)

A Multi-Tenant SaaS platform designed to digitize inventory management for construction and interior design companies. This system replaces fragmented spreadsheet workflows with a centralized cloud solution and a real-time public catalog.

> **Note:** The live application interface and data are in **Spanish**, as it targets the Colombian B2B market.

---

## 🎯 The Problem vs. The Solution

**Before (The Problem):**
- Manual inventory control spread across 10+ disconnected Excel spreadsheets.
- Human errors in stock entry/exit causing physical stock discrepancies.
- High volume of customer inquiries regarding photo availability and stock via WhatsApp.

**After (The Solution):**
- **Centralized Administration:** A web-based dashboard for real-time inventory tracking, including logs and user audits.
- **Automated Catalog:** Customers can browse real-time stock, filter by categories, and generate quotation requests that are sent directly to the business's WhatsApp, saving hours of manual customer service.

---

## ✨ Core Features

### Public Facing Site (`/`, `/catalog`, `/about`)
- **Real-time Product Catalog:** Dynamic filtering by category.
- **Live Stock Status:** Visible availability indicators (In Stock / Out of Stock).
- **Quotation System:** Automated WhatsApp message generation from the shopping cart.

### Admin Dashboard (`/inventory`, `/admin`)
- **Full CRUD Management:** Create, edit, and delete products seamlessly.
- **Stock Auditing:** Transaction history (In/Out) with user-specific logs.
- **Advanced Filtering:** View history by product, type, or date.
- **Image Management:** Automatic compression and hosting via Supabase Storage.
- **Smart Alerts:** Notifications for low-stock or out-of-stock items.

---

## 🛠️ Tech Stack

| Layer | Technology |
|------|-----------|
| **Framework** | Next.js 15 (App Router) |
| **UI** | React 19 + Tailwind CSS v4 |
| **Backend / DB** | Supabase (PostgreSQL) |
| **Storage** | Supabase Storage |
| **Auth** | Supabase Auth |
| **Deployment** | Vercel |

---

## ⚙️ Multi-tenancy Architecture

The system is built on a **Shared Database, Isolated Data** model. Each business operates under a unique `tenant_id`.
- All queries are scoped to the specific `tenant_id` to ensure data privacy.
- Admin users are authenticated with metadata-level validation to prevent cross-tenant access.
- This allows a single deployment to serve multiple businesses while maintaining completely separate datasets.
