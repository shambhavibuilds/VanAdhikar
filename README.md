# FRA Atlas — AI-Powered WebGIS Decision Support System

**Smart India Hackathon 2025 | Problem Statement SIH12508**
**Ministry of Tribal Affairs (MoTA)**

## Problem Statement

Development of an AI-powered FRA Atlas and WebGIS-based Decision Support System (DSS) for Integrated Monitoring of Forest Rights Act (FRA) Implementation.

*Focus states: Madhya Pradesh, Tripura, Odisha, Telangana*

## Overview

The Forest Rights Act (2006) recognizes the land rights of tribal and forest-dwelling communities across India. In practice, implementation is hampered by scattered paper records, inconsistent land verification, poor awareness of eligible government schemes, and weak transparency in the claims process.

**FRA Atlas** digitizes legacy land records, overlays them on satellite imagery for verification, tracks claims through their full lifecycle, and connects verified claimants to relevant government welfare schemes — while keeping the process visible and accountable to the Gram Sabha (village council) itself.

## Core Features

### 1. Digital Records & Claims Management
- Digitization of legacy paper land records
- End-to-end claim lifecycle tracking: Submitted → Under Review → Approved / Rejected → Appeal
- Appeal workflow with auto-routing to the next reviewing authority

### 2. WebGIS & Satellite Verification
- Interactive map of claimed land parcels using satellite imagery overlays
- AI-assisted mismatch flagging between claimed land use and satellite data
- **Flags are advisory only** — every flagged parcel requires human (Gram Sabha / Forest Rights Committee) review before any rejection

### 3. Scheme Integration
- Automatic matching of verified claimants to eligible government welfare schemes

### 4. Transparency Features
- Public Gram Sabha dashboard for community-level claim visibility
- Multilingual audio support for low-literacy users
- SMS / WhatsApp status updates to claimants

### 5. Security & Governance
- Role-based access control (Admin / Forest Official / Gram Sabha Member / Public Viewer)
- Encrypted data storage
- Immutable audit log of every record view/edit/approval, tied to official ID and timestamp
- "Protected status" flag: land under an active, Gram Sabha–verified claim cannot be marked "available" or actioned by another department until the FRA process is formally closed

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React.js / Next.js, Tailwind CSS |
| Map / GIS | Leaflet.js (or Mapbox GL JS) |
| Backend | Node.js + Express (or Python + FastAPI) |
| Database | PostgreSQL + PostGIS |
| Satellite Imagery | Sentinel Hub / Google Earth Engine (free tier) |
| AI Mismatch Detection | Simplified rule-based / pre-trained classification (proof-of-concept) |
| Multilingual & Audio | Google Cloud TTS / Web Speech API, Google Translate API |
| Notifications | Twilio (SMS demo) / simulated WhatsApp UI |
| Auth | JWT-based authentication |
| Hosting | Vercel/Netlify (frontend), Render/Railway (backend + DB) |

## Architecture (High Level)

```
[React Frontend]
   ├── Gram Sabha Dashboard
   ├── Claim Submission & Status Tracker
   ├── Interactive Map (Leaflet + Satellite Layer)
   └── Multilingual / Audio Toggle
          │
          ▼
[Express/FastAPI Backend]
   ├── Auth & Role-Based Access Middleware
   ├── Claims API (CRUD + status transitions)
   ├── AI Mismatch Flagging Service
   ├── Notification Service (SMS/WhatsApp mock)
   └── Audit Logging Service
          │
          ▼
[PostgreSQL + PostGIS]
   ├── Claimants
   ├── Land Parcels (geospatial)
   ├── Claims & Status History
   └── Audit Logs
```

## Team

| Member | Role |
|---|---|
| Member A | Frontend & UI/UX |
| Member B | Backend & Database |
| Member C | Map/GIS & AI Demo Layer |

## Roadmap

- **Day 1:** Repo setup, DB schema, auth skeleton, base UI, map with dummy data
- **Day 2:** Claim CRUD + status flow, live dashboard, real markers on map, satellite layer integration
- **Day 3:** AI mismatch flag simulation, multilingual/audio support, notification mock, audit log, protected-status flag
- **Day 4:** Bug fixes, UI polish, pitch deck, dry-run demos

## Known Limitations (Hackathon Scope)

- AI land-use classification is a simplified proof-of-concept, not production-grade computer vision
- WhatsApp integration is simulated (no live Business API approval within timeframe)
- Single-state instance for demo purposes; multi-state federated architecture is a proposed future extension

## Future Scope

- Federated per-state deployment with a shared data standard for national aggregation
- Offline-first PWA support for low-connectivity forest regions
- Independent/public read-only access to aggregated (non-personal) transparency data
- Production-grade satellite land-use classification model trained on region-specific data

## License

Built for Smart India Hackathon 2025 — Ministry of Tribal Affairs problem statement (SIH12508).
# VanAdhikar
