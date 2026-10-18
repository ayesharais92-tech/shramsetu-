# SHRAMSETU (श्रमसेतु)
### Cooperative Gig Services Platform for Household & Community Services
**Smart India Hackathon (SIH 2026) — Problem Statement ID: 26089**  
**Theme:** Agriculture, FoodTech & Rural Development | **Category:** Software  

---

> *"Urban Company digitizes home services; **SHRAMSETU** digitizes the cooperative workforce behind local services."*

---

## 📌 Executive Summary

SHRAMSETU is an institutional digital marketplace built for Primary Agricultural Credit Societies (PACS), Urban Labor Cooperatives, and State Cooperative Federations. Unlike venture-backed gig aggregators that extract 25–35% platform commission and treat workers as expendable contractors, SHRAMSETU empowers certified cooperative artisans with:

- **Institutional Co-Ownership & Governance**: Democratic federation oversight through National Council for Cooperative Training (NCCT) standards.
- **88% Direct Artisan Living Wage**: Transparent fee architecture (88% Artisan + 7% Cooperative Welfare Fund + 5% Platform Maintenance).
- **10-Stage Deterministic State Machine**: Guaranteed state transition integrity from `REQUESTED` through `ARRIVED` to `PAID` and `RATED`.
- **Touch-Friendly Mobile Worker Controls**: Large, high-contrast actions (`[Start Travel]`, `[I've Arrived]`, `[Verify OTP & Start]`, `[Complete Service]`, `[Request Payment]`).
- **5-Pillar Digital Skill Passport**: QR-verified identity, residential clearance, NCCT certification level, police background verification, and peer rating.
- **Worker Welfare & Insurance Center**: Consolidated coverage across Government Schemes (PMSBY/PMJJBY), Group Accident covers, and Federation emergency health grants.
- **Cooperative Capitalization Model**: Affordable ₹6,000 platform registration share with transparent 6-month installment tracking (₹1,000/mo).
- **AI Demand Intelligence & Workforce Allocation**: Real-time spatio-temporal booking telemetry driving predictive labor allocation across municipal wards.

---

## ⚙️ Technology Stack

| Layer | Technologies |
| :--- | :--- |
| **Frontend UI** | React 19, Vite, Vanilla CSS Design System, Responsive Mobile-First Device Frame |
| **Design Language**| Custom Saffron/Teal/Navy Cooperative Palette (`#0B2545`, `#FF9933`, `#138808`), Lucide Icons |
| **State Management**| In-memory Reactive `PlatformContext` with deterministic finite state machine rules |
| **Telemetry & Maps**| OpenStreetMap & Leaflet interactive spatial tracking with route simulation |
| **Code Quality** | Oxlint (`@oxlint/binding-win32-x64-msvc`), Zero-warning builds |
| **AI / Decision Support**| Spatio-temporal demand forecaster prototype with heuristic workforce balancing |
| **Security & Privacy** | Dual-Factor Admin 2FA, Differential Privacy (Strict redaction of police audit logs for consumers) |

---

## 🏛️ System Architecture & Workflow

```
CUSTOMER                         WORKER                        FEDERATION ADMIN
   │                                │                                 │
   │ 1. Find & Book Service         │                                 │
   ├───────────────────────────────►│                                 │
   │                                │ 2. Accept Job                   │
   │                                │                                 │
   │                                │ 3. Start Travel (GPS Telemetry) │
   │◄────── Live Route Map ─────────┤                                 │
   │                                │                                 │
   │                                │ 4. Mark Arrived                 │
   │◄────── Status: ARRIVED ────────┤                                 │
   │                                │                                 │
   │ 5. Provide 4-Digit OTP         │                                 │
   ├───────────────────────────────►│ 6. Start Service                │
   │                                │                                 │
   │                                │ 7. Complete Service             │
   │◄────── Status: COMPLETED ──────┤                                 │
   │                                │                                 │
   │ 8. Pay ₹850 via UPI            │                                 │
   ├───────────────────────────────►│ 9. 88% Direct Artisan Disbursal │
   │                                │                                 │
   │ 10. Rate & Review 5★           │                                 │
   ├───────────────────────────────►│                                 │
   │                                │                                 │
   │                                │                                 │ 11. AI Demand Forecast
   │                                │                                 │ 12. Dynamic Labor Allocation
   │                                │                                 │ 13. Adjudicate Insurance Claims
   │                                │                                 │ 14. Audit Background Checks
```

---

## 🚀 Key Modules & Capabilities

### 1. Complete 10-Stage Job Lifecycle Tracking
- **Lifecycle Pipeline**: `REQUESTED` ➔ `MATCHED` ➔ `ACCEPTED` ➔ `ON_THE_WAY` ➔ `ARRIVED` ➔ `SERVICE_STARTED` ➔ `SERVICE_COMPLETED` ➔ `PAYMENT_PENDING` ➔ `PAID` ➔ `RATED`.
- **State Machine Integrity**: Backend-equivalent validation rejects illegal jumps (e.g., `ACCEPTED` ➔ `COMPLETED` is strictly prohibited).
- **Auto-Replacement Matching**: If a worker cancels an accepted booking, the platform triggers automated instant re-matching, presenting the customer with a top-scoring alternative artisan.

### 2. Worker-Controlled Touch-First Job Operations
- Large, glove-friendly buttons designed for mobile workers on the field.
- Integrated customer PIN verification to prevent fraudulent service commencement.
- Post-service payment request triggering real-time customer settlement invoices.

### 3. Worker Welfare & Insurance Center
- **Policy Explorer**: Categorized policies spanning Government Schemes (PMSBY/PMJJBY), Federation Accident covers, and Private Hospitalization.
- **Interactive Claim Desk**: File claims with incident dates, claimed amounts, and evidence notes.
- **Federation Review**: Federation Directors can review, approve, or reject claims with full audit trail logging.

### 4. Registration Platform Fee & Installments
- Configurable ₹6,000 cooperative equity registration fee.
- 6-Month installment plan tracker displaying paid installments, remaining balance, and one-click demo installment settlement.

### 5. 4-Tier Skill Development & Digital Certificates
- **Levels**: Level 1 (Unskilled), Level 2 (Beginner), Level 3 (Medium Skilled), Level 4 (Advanced Master).
- **Progress Tracking**: Course modules, live quiz scores, and practical assessments.
- **Verifiable Digital Certificates**: Issued upon course completion with unique synthetic Certificate IDs (`SHR-CERT-XXXX`).

### 6. Digital Skill Passport & Background Verification
- **5-Pillar Verification**: Identity (Aadhaar Sandbox), Address Verification, NCCT Skill Testing, Police Background Clearance, and Cooperative Standing.
- **Privacy Architecture**: Customers only see `✓ Background Verified` with a green shield; sensitive police file numbers and officer inspection notes are restricted to Federation Admin audit logs.

### 7. AI Demand Forecasting & Dynamic Workforce Allocation
- Spatio-temporal demand predictions across 4 urban sectors (Sector 7, Civil Lines, Karol Bagh, Rohini).
- Workforce deficit alerts with one-click administrative labor reallocation actions (`[Accept]`, `[Reject]`, `[Manual Reallocate]`).

---

## 🔐 Credentials & Quick Demo Logins

The application features instant 1-click demo logins on the navigation bar:

| Role | Portal / Action | Default Credentials |
| :--- | :--- | :--- |
| **Customer** | Top-right "Customer" toggle | Demo Customer (Sector 7, Dwarka) |
| **Worker** | Top-right "Worker" toggle | **Raj Kumar** (Master Electrician, ID: `WRK-101`) |
| **Federation Admin** | "Officer Portal" in Navbar | `director@delhicoop.gov.in` / `Admin@2026` (2FA: `789012`) |
| **NCCT Officer** | "Officer Portal" in Navbar | `officer@ncct.gov.in` / `Ncct@2026` (2FA: `451089`) |

---

## ⏱️ Five-Minute SIH Presentation Script (Judges' Walkthrough)

1. **Step 1 — Landing Page (0:00 - 0:45)**
   - Highlight the banner: *"Trusted Local Services. Powered by Cooperative Workers."*
   - Mention the 88% artisan split vs 70% in traditional aggregators.
2. **Step 2 — Smart Matching (0:45 - 1:30)**
   - As Customer, select **Electrical Repair**.
   - Show the **96% Smart Match** card for Raj Kumar (Skill 50%, Availability 30%, Proximity 20%).
   - Click **"View Skill Passport"** to showcase verified NCCT Level 4 credentials and background verification status.
3. **Step 3 — Booking & Worker Operations (1:30 - 2:45)**
   - Book the service.
   - Switch to **Worker View**. Notice the active job card.
   - Click **[Start Travel]** ➔ Switch to Customer to show the live map update and ETA timer.
   - Click **[I've Arrived]** ➔ **[Verify OTP & Start Service]** (Enter OTP `4921`).
   - Click **[Complete Service]** ➔ **[Request Payment]**.
4. **Step 4 — Transparent Payment & Rating (2:45 - 3:30)**
   - Switch to Customer View. The payment modal opens showing ₹850 split:
     - Worker Living Wage: ₹748 (88%)
     - Cooperative Social Security: ₹60 (7%)
     - NCCT Platform Fee: ₹42 (5%)
   - Complete payment with demo UPI and submit 5★ rating.
5. **Step 5 — Worker Welfare & Skill Academy (3:30 - 4:15)**
   - On Worker Dashboard, visit **Training Center** (view modules & printable certificate).
   - Visit **Insurance Center** (show PMSBY policy and submit a sample claim).
   - Visit **Registration Fee** (show 6-month installment progress bar).
6. **Step 6 — Federation Command Center (4:15 - 5:00)**
   - Log into **Officer Portal**.
   - Review **Background Verification Desk** (confidential police verification audit trail).
   - Review **AI Demand Forecaster** & click **[Accept Allocation]** to reallocate 4 electricians to Sector 7.
   - Conclude: *"SHRAMSETU transforms precarious gig labor into dignified, cooperative-owned digital careers."*

---

## ⚖️ Honest Prototype Disclosures (SIH 2026 Guidelines)

To maintain absolute transparency with evaluators:

| Feature | Classification | Description |
| :--- | :--- | :--- |
| **Booking State Machine** | **LIVE / WORKING PROTOTYPE** | Full deterministic state enforcement and real-time event propagation |
| **Transparent Payment Split** | **LIVE / WORKING PROTOTYPE** | Real mathematical split (88/7/5) and dynamic client-side receipt generation |
| **Digital Skill Passport** | **LIVE / WORKING PROTOTYPE** | Verified credentials modal with dynamic worker profile hydration |
| **Role-Based Portals** | **LIVE / WORKING PROTOTYPE** | Customer, Worker, Federation Director, and NCCT Officer views |
| **GPS / Route Tracking** | **SIMULATED / DEMO TRACKING** | Map displays live route simulation; production will hook to React Native Geolocation |
| **Payment Gateway** | **DEMO PAYMENT** | Emulates UPI transaction flow; production will hook to Razorpay/Cashfree |
| **Background Checks** | **INTEGRATION READY** | Synthetic police records; production connects to CCTNS / DigiLocker APIs |
| **AI Demand Forecasting**| **DEMO FORECAST / ROADMAP** | Spatio-temporal simulation; production connects to PyTorch LSTM / Prophet microservice |

---

## 🛠️ Local Installation & Development

```bash
# Clone repository
git clone https://github.com/your-org/shramsetu.git
cd sih2026-main

# Install dependencies
npm install

# Run Oxlint validation
npm run lint

# Build production bundle
npm run build

# Start development server
npm run dev
```

App will run on `http://localhost:5173/`.
