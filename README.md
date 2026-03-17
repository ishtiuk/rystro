<div align="center">

  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:f59e0b,100:ea580c&height=150&section=header&text=RysTRO&fontSize=50&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=Restaurant%20Management%20Software&descSize=18&descAlignY=55&descColor=d4d4d8" width="100%" />

</div>

<div align="center">

  <a href="https://rystro.com"><img src="https://img.shields.io/badge/Live-rystro.com-f59e0b?style=for-the-badge&logo=googlechrome&logoColor=black" /></a>
  <a href="https://rystro.com/restaurants"><img src="https://img.shields.io/badge/Directory-Restaurants-ea580c?style=for-the-badge" /></a>

  <br/><br/>

  **An all-in-one restaurant management SaaS — POS, billing, table management, kitchen orders, inventory tracking, analytics, and digital menus.**

  *Actively used by multiple restaurant clients in daily operations across Bangladesh.*

</div>

---

## Features

| Module | Description |
|--------|------------|
| **POS & Billing** | Fast point-of-sale with cash, card, and online payment methods. Service charge, VAT, discounts |
| **Table Management** | Visual table grid with real-time status — Empty, Occupied, Billing. Dine-in order flow |
| **Kitchen Order Tickets (KOT)** | Auto-print KOT slips to kitchen printer via WebSocket. Multi-station support (Kitchen, Juice Bar, etc.) |
| **Thermal Printing** | ESC/POS silent printing via WebUSB + Web Serial. Supports Epson, Star, Rongta, Xprinter, Goojprt |
| **Inventory & Items** | Product management with categories, images, stock tracking, cost/price, packaged vs cooked items |
| **Digital Menu** | Public menu page (`/m/:slug`) — shareable on Google Maps, Facebook, WhatsApp. Dark/light mode, EN/BN bilingual |
| **Analytics & Reports** | Sales trends, top products, payment breakdown, daily/weekly/monthly reports, low stock alerts |
| **Staff Management** | Role-based access (Owner, Manager, Cashier), staff profiles, salary tracking |
| **Multi-Branch** | Multi-tenant architecture — each restaurant is isolated with its own data, settings, and users |
| **Finance & Expenses** | Track purchases, suppliers, expenses. Supplier ledger, payment history |
| **Bilingual** | Full English + Bengali (বাংলা) support with Bengali numerals and BDT/USD currency formatting |

---

## Tech Stack

<div align="center">

![React](https://img.shields.io/badge/React_18-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![shadcn/ui](https://img.shields.io/badge/shadcn/ui-000?style=for-the-badge&logo=shadcnui&logoColor=white)

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=for-the-badge&logo=sqlalchemy&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)

</div>

---

## Architecture

```
┌───────────────────────────────────────────────┐
│                  Frontend                     │
│  React 18 + TypeScript + Vite + Tailwind      │
│  shadcn/ui + PWA + IndexedDB image cache      │
├───────────────────────────────────────────────┤
│             WebSocket / REST API              │
├───────────────────────────────────────────────┤
│                  Backend                      │
│  FastAPI + SQLAlchemy (async) + Alembic       │
│  JWT Auth + RBAC + Multi-tenant isolation     │
├───────────────────────────────────────────────┤
│                  Database                     │
│  PostgreSQL 15 (UUID PKs, tenant-scoped)      │
├───────────────────────────────────────────────┤
│                  Printing                     │
│  ESC/POS → WebUSB (Epson/Star)               │
│          → Web Serial (Rongta/Xprinter)      │
│          → Browser iframe (fallback)         │
├───────────────────────────────────────────────┤
│                  Hosting                      │
│  Cloud (SaaS, multi-tenant)                   │
└───────────────────────────────────────────────┘
```

---

## Key Highlights

- **Silent thermal printing** — no print dialog. WebUSB for branded printers, Web Serial for Chinese USB-serial printers
- **Real-time sync** — waiter places order on tablet → KOT auto-prints in kitchen → table status updates on cashier screen
- **12h client-side cache** on public menu pages — near-zero server load from digital menu visitors
- **Rate limited public API** — 10 req/min per IP on public endpoints
- **Offline-first image caching** — product images stored in IndexedDB, zero network requests on repeat visits
- **Multi-currency** — supports 25+ currencies with proper locale formatting

---

## Live

- **App**: [rystro.com](https://rystro.com)
- **Restaurant Directory**: [rystro.com/restaurants](https://rystro.com/restaurants)
- **Sample Menu**: [rystro.com/m/chayer-gram](https://rystro.com/m/chayer-gram)

---

<div align="center">

  Built & maintained by **[Md. Ishtiuk Ahammed](https://github.com/ishtiuk)** — Founder & CTO of **[Archexify](https://facebook.com/archexify)**

  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:f59e0b,100:ea580c&height=80&section=footer" width="100%" />

</div>
