# 🛵 GigShield — AI-Powered Parametric Income Insurance for Food Delivery Partners

> **Guidewire DEVTrails 2026 | University Hackathon**
> Protecting the livelihoods of India's Zomato & Swiggy delivery partners against uncontrollable external disruptions.

---

## 📌 Table of Contents

1. [Problem Statement](#problem-statement)
2. [Our Solution](#our-solution)
3. [Persona & Real-World Scenarios](#persona--real-world-scenarios)
4. [Application Workflow](#application-workflow)
5. [Weekly Premium Model](#weekly-premium-model)
6. [Parametric Triggers](#parametric-triggers)
7. [AI/ML Integration Plan](#aiml-integration-plan)
8. [Adversarial Defense & Anti-Spoofing Strategy](#adversarial-defense--anti-spoofing-strategy)
9. [Tech Stack](#tech-stack)
10. [Development Plan](#development-plan)
11. [Team](#team)

---

## Problem Statement

India has over **11 million food delivery partners** working for platforms like Zomato and Swiggy. They earn between ₹600–₹900 per day, operating entirely on a gig basis with no fixed salary and no safety net.

When external disruptions strike — a Mumbai monsoon flood, a Delhi AQI red alert, a sudden local curfew — these workers lose **20–30% of their monthly income overnight.** They cannot work. The orders stop. The money stops. But their rent, EMIs, and family expenses do not.

**Currently, no platform offers parametric income protection for these workers.** Existing insurance products cover health and accidents — not the hours they simply couldn't work because the city shut down around them.

**GigShield fixes this.**

---

## Our Solution

**GigShield** is an AI-powered parametric insurance platform that:

- Automatically detects external disruptions using real-time data (weather, AQI, traffic, civic alerts)
- Triggers income compensation claims **without the worker doing anything**
- Processes payouts to UPI/bank accounts **within minutes**
- Uses **weekly pricing** aligned to the gig worker's earnings cycle
- Employs **multi-signal fraud detection** to protect the liquidity pool

> **Coverage scope:** Loss of income ONLY. We strictly exclude health, life, accident, and vehicle repair coverage.

---

## Persona & Real-World Scenarios

### Our Persona: The Urban Food Delivery Partner

| Attribute | Details |
|---|---|
| Platform | Zomato / Swiggy |
| City | Mumbai, Delhi (Phase 1); pan-India scale planned |
| Daily working hours | 10:00 AM – 11:00 PM (peak: 12–2 PM lunch, 7–10 PM dinner) |
| Average daily earnings | ₹700–₹900 |
| Average weekly earnings | ₹4,500–₹5,500 |
| Income type | Per delivery (₹35–₹65/order) + surge bonuses |
| Payment cycle | Weekly payouts from platform |
| Biggest risk | Losing peak dinner/lunch hours to weather or civic disruptions |

---

### Scenario 1 — Mumbai Monsoon Flood 🌧️

**Worker:** Arjun, 26, Swiggy partner, Andheri East, Mumbai

**Event:** IMD issues red alert. Rainfall exceeds 65mm/hour. Waterlogging reported across Andheri, Kurla, Dharavi zones. Platform orders drop 80%.

**Without GigShield:** Arjun stays home. Loses entire dinner rush — approximately ₹480 in lost earnings.

**With GigShield:**
- Weather API detects rainfall >60mm in Arjun's delivery zone (pin code level)
- System cross-checks: Arjun was active on Swiggy app until 30 mins before rain peak
- Fraud check passes (movement data + no home WiFi conflict)
- Claim auto-initiated. ₹400 payout processed to Arjun's UPI in 8 minutes.
- Arjun receives a push notification: *"We've got you covered. ₹400 credited to your account."*

---

### Scenario 2 — Delhi AQI Red Alert 💨

**Worker:** Salim, 31, Zomato partner, Rohini, Delhi

**Event:** Delhi AQI spikes to 420 (Severe). GRAP Stage IV imposed. Government advisory against outdoor activity.

**Without GigShield:** Salim risks his health or loses the full day. No compensation either way.

**With GigShield:**
- AQI monitoring detects >400 in Salim's registered zone
- Duration of alert logged (12 hours = full working day lost)
- Payout calculated based on Salim's 4-week average daily earnings
- ₹650 credited within 15 minutes. Zero action required from Salim.

---

### Scenario 3 — Sudden Local Bandh / Curfew 🚫

**Worker:** Priya, 28, Swiggy partner, Nagpur

**Event:** Unplanned local strike. Roads blocked. Restaurants closed in 3 key zones from 6 PM–11 PM.

**Without GigShield:** Priya loses her best 5 earning hours with no recourse.

**With GigShield:**
- Civic disruption API (simulated mock in Phase 1) detects verified strike/curfew in Nagpur zones
- Partial disruption payout calculated (5 hours out of 13 working hours)
- Pro-rated payout of ₹270 processed automatically.

---

## Application Workflow

```
┌─────────────────────────────────────────────────────────────────┐
│                        WORKER JOURNEY                           │
└─────────────────────────────────────────────────────────────────┘

STEP 1 — ONBOARDING (2 minutes)
  Worker downloads GigShield app
  → Enters: Name, city, pin code, delivery platform (Zomato/Swiggy)
  → Links UPI ID for payouts
  → Grants location permission (for zone-based risk profiling)
  → Verified against mock platform API (worker is active on Zomato/Swiggy)

STEP 2 — AI RISK PROFILING (Instant)
  AI engine analyzes:
  → Worker's city + delivery zone (flood/AQI historical risk score)
  → Historical disruption frequency in their pin code
  → Platform activity level (avg. weekly earnings declared)
  → Generates: Risk Score (Low / Medium / High)

STEP 3 — POLICY CREATION (Worker chooses tier)
  Three weekly plans displayed:
  → Basic Shield    | ₹29/week | Up to ₹800/week coverage
  → Standard Shield | ₹49/week | Up to ₹1,500/week coverage
  → Max Shield      | ₹79/week | Up to ₹2,500/week coverage
  Premium auto-adjusted by AI risk score (±₹5–₹15)
  Worker pays weekly via UPI auto-debit

STEP 4 — CONTINUOUS MONITORING (24/7 Automated)
  GigShield monitors in real-time:
  → OpenWeatherMap API (rainfall, temperature, storm alerts)
  → AQI monitoring API (CPCB data / IQAir)
  → Traffic disruption API (Google Maps / mock)
  → Civic alert feed (mock government alert API)

STEP 5 — DISRUPTION DETECTED → AUTO CLAIM
  Trigger fires when threshold crossed in worker's zone
  → Fraud detection engine runs (multi-signal check)
  → Claim auto-initiated (zero action from worker)
  → Payout calculated based on disruption duration + worker's avg earnings
  → Money sent to UPI in <15 minutes (Tier 1 clean claims)

STEP 6 — WORKER DASHBOARD
  Worker sees in real-time:
  → Active policy status + coverage this week
  → Live disruption alerts in their city
  → Payout history
  → "Earnings Protected" total since joining
```

---

## Weekly Premium Model

### Why Weekly?

Food delivery partners are paid weekly by Zomato and Swiggy. They do not think in monthly terms. A ₹199/month insurance feels like a large commitment. A ₹49/week insurance feels like skipping one chai.

Weekly pricing also means:
- Workers can pause coverage in weeks they take personal leave
- Premium adjusts dynamically week-to-week based on forecast risk
- Aligns perfectly with their UPI weekly platform payout

### Pricing Tiers

| Plan | Weekly Premium | Max Weekly Payout | Best For |
|---|---|---|---|
| Basic Shield | ₹29/week | ₹800 | Part-time workers, <₹3,000/week earners |
| Standard Shield | ₹49/week | ₹1,500 | Full-time workers, avg. earners |
| Max Shield | ₹79/week | ₹2,500 | High-earning riders, peak-city workers |

### Dynamic Premium Calculation (AI-Driven)

Base premium is adjusted by the AI Risk Engine using:

```
Final Weekly Premium = Base Premium × Zone Risk Multiplier × Season Factor × Activity Factor

Zone Risk Multiplier:
  → Flood-prone zone (historical floods >3/year)  : +15%
  → High AQI zone (Delhi winters)                  : +10%
  → Low-risk zone (historically stable)            : -10%

Season Factor:
  → Monsoon months (June–September)               : +20%
  → Winter pollution months (Nov–Jan, North India) : +15%
  → Standard months                               : 0%

Activity Factor:
  → Worker active >6 days/week (higher exposure)  : +5%
  → Worker active <3 days/week (lower exposure)   : -5%
```

**Example:** Arjun (Mumbai, Andheri, Standard Shield, July)
> ₹49 × 1.15 (flood zone) × 1.20 (monsoon) = **₹67.62/week** → rounded to ₹68/week

### Payout Calculation

```
Payout = (Worker's Avg Daily Earnings ÷ Working Hours/Day) × Disrupted Hours × Coverage %

Coverage % by plan:
  Basic Shield    → 60% of lost income
  Standard Shield → 75% of lost income
  Max Shield      → 90% of lost income
```

---

## Parametric Triggers

Parametric insurance means: **no manual claims.** The system pays automatically when a measurable threshold is crossed. Here are our 5 triggers:

| # | Trigger | Data Source | Threshold | Payout Type |
|---|---|---|---|---|
| 1 | Heavy Rainfall | OpenWeatherMap API | >40mm/hour in worker's pin code | Per-hour payout for duration |
| 2 | Severe AQI | CPCB / IQAir API | AQI >300 (Very Poor) in worker's zone | Full/half-day payout |
| 3 | Extreme Heat | OpenWeatherMap API | Temperature >44°C for >3 hours | Half-day payout |
| 4 | Flood Alert | IMD / mock civic API | Red/orange flood alert in district | Full-day payout |
| 5 | Civic Disruption | Mock government alert API | Verified curfew/bandh in delivery zone | Pro-rated payout by hours affected |

### Trigger Logic Example (Rainfall)

```
IF rainfall_mm_per_hour > 40
  AND location_pin_code MATCHES worker_registered_zone
  AND disruption_duration > 1 hour
  AND worker_was_active IN last 2 hours (platform API check)
THEN:
  → Initiate claim
  → Run fraud check
  → Calculate payout
  → Process UPI transfer
```

---



## AI/ML Integration Plan

### 1. Dynamic Risk Scoring & Premium Calculation

**Model type:** Gradient Boosted Decision Tree (XGBoost) — or rule-based scoring engine for Phase 1

**Input features:**
- Worker's delivery zone + historical weather disruption frequency
- City tier (Mumbai vs Tier-2 city)
- Season/month
- Worker's activity pattern (days/week active)
- Local flood/AQI risk index

**Output:** Risk score (0–100) → maps to premium multiplier

**Phase 1:** Rule-based scoring with hardcoded risk tables (Mumbai monsoon = high risk)
**Phase 2:** Train on historical weather + claim data, deploy ML model

---

### 2. Payout Calculation Engine

**Logic:** Rule-based in Phase 1
- Worker's self-declared average daily earnings (verified loosely against platform tier)
- Disruption duration (from API data)
- Coverage percentage (by plan tier)
- Output: Rupee payout amount

---

### 3. Fraud Detection Engine (Multi-Signal)

**Model type:** Anomaly detection (Isolation Forest) — rule-based scoring for Phase 1

**Signals analyzed:**
- GPS location vs registered zone
- WiFi SSID (is worker at home?)
- Device accelerometer (is worker moving?)
- Claim timing vs alert timing
- Platform activity history
- Coordinated claim volume spike

**Full details in Adversarial Defense section below.**

---

### 4. Predictive Risk Dashboard (Phase 3)

**Model type:** Time-series forecasting (Prophet / ARIMA)

**Purpose:** Predict next week's likely claims based on weather forecast
- Helps insurer manage liquidity pool proactively
- Alerts admin if expected payouts exceed 70% of pool

---

## Adversarial Defense & Anti-Spoofing Strategy

> This section addresses the critical vulnerability identified in the DEVTrails 2026 threat briefing: a coordinated syndicate of workers using GPS-spoofing applications to fake locations in weather-alert zones and drain the liquidity pool.

---

### 1. The Differentiation — Real Stranded Worker vs GPS Spoofer

The core insight is this: **a genuine stranded worker and a GPS spoofer leave completely different digital signatures.** Our system does not rely on GPS alone. It builds a multi-signal trust score from 6 independent data channels.

#### Genuine Stranded Worker Profile:
- Shows continuous GPS movement in delivery zone for hours **before** the disruption
- Platform shows active order acceptance until weather worsened
- Device accelerometer confirms bike-riding motion pattern prior to halt
- Cell tower ID matches GPS coordinates
- Network signal degrades (real storms degrade signal)
- GPS coordinates drift slightly (real outdoor GPS in storms is imprecise)

#### GPS Spoofer Profile:
- GPS coordinates **jump instantly** to flood zone (teleportation, not travel)
- Phone is connected to **home WiFi network** while GPS claims outdoor location ← single strongest signal
- Accelerometer shows **zero movement** (sitting at home)
- Cell tower ID contradicts GPS location
- Perfect GPS signal in supposed storm zone (spoof apps produce unrealistically clean signals)
- Zero platform activity all day before the claim

#### Trust Score Formula (Phase 1 — Rule Based):

```
Trust Score = 100 (start)

DEDUCTIONS:
  Home WiFi detected while GPS shows field location     → -40 points
  GPS jumped >5km in <2 minutes                         → -30 points
  Zero accelerometer movement for past 60 minutes       → -20 points
  Cell tower location contradicts GPS by >3km           → -25 points
  No platform activity in 4+ hours before claim         → -15 points
  Claim filed within 60 seconds of alert firing         → -10 points
  Perfect GPS signal strength in declared storm zone    → -10 points

RESULT:
  Score 70–100 → Tier 1: Auto-approve, instant payout
  Score 40–69  → Tier 2: Soft flag, 2-hour passive recheck
  Score 0–39   → Tier 3: Hard flag, 24-hour human review
```

---

### 2. The Data — Beyond Basic GPS

#### Device-Level Signals:

| Signal | What It Detects | Implementation |
|---|---|---|
| WiFi SSID & BSSID | Worker connected to home network | React Native `NetInfo` API |
| Accelerometer | Is device physically moving? Bike pattern? | React Native `expo-sensors` |
| Gyroscope | Vibration pattern matches outdoor riding | React Native `expo-sensors` |
| GPS accuracy radius | Spoofed GPS is unnaturally precise | Native GPS accuracy field |



#### Behavioral Signals:

| Signal | What It Detects | Implementation |
|---|---|---|
| Platform activity log | Was worker online before disruption? | Mock Zomato/Swiggy API |
| Delivery history today | Any completed deliveries before claim? | Mock platform API |
| Historical claim pattern | Claiming every single week? | Our database |
| Account age | New account + instant claim = suspicious | Our database |
| Referral chain | Syndicate members often join via same link | Graph database query |

#### Coordinated Ring Detection:

```
RING DETECTION ALGORITHM:

1. Monitor claim volume per zone per 5-minute window
   IF claims_in_zone_in_5min > 20 → FLAG entire batch for review

2. Analyze account creation dates of claimants
   IF >30% of claimants in a batch joined within same 14-day window → FLAG

3. Social graph analysis
   IF >15 claimants share same referral code → FLAG as possible syndicate

4. Device fingerprint check
   IF multiple accounts filing from same physical device → BLOCK + FLAG

5. Velocity check
   IF same worker files claims on 4+ consecutive weeks → MANUAL REVIEW trigger
```

---

### 3. The UX Balance — Flagged Claims Without Penalizing Honest Workers

This is the most important design principle of our fraud system: **innocent workers must never feel punished.** Bad weather causes real network drops, GPS drift, and phone connectivity issues. Our system is built around this reality.

#### Three-Tier Response System:

**🟢 Tier 1 — Auto-Approve (Trust Score 70–100)**
- All signals clean, no anomalies
- Worker has good history
- **Action:** Payout processed immediately, <15 minutes
- **Worker experience:** Push notification — *"GigShield has you covered. ₹X credited to your UPI."*
- No friction whatsoever.

**🟡 Tier 2 — Soft Flag (Trust Score 40–69)**
- 1–2 minor anomalies (e.g., weak GPS due to storm, slight signal inconsistency)
- This is the most common scenario for **genuine workers in actual bad weather**
- **Action:** System waits 90 minutes and passively re-checks signals
- **Worker experience:** Notification — *"We're confirming your coverage due to network conditions in your area. Your payout will be processed within 2 hours — no action needed from you."*
- Worker does NOT need to do anything. System re-checks on its own.
- If re-check clears → auto-pays. If re-check flags harder → escalates to Tier 3.

**🔴 Tier 3 — Hard Flag (Trust Score 0–39)**
- Multiple serious anomalies present (home WiFi + zero movement + GPS jump)
- **Action:** Claim held for 24-hour human review
- **Worker experience:** Notification — *"Your claim is being reviewed by our team. We'll update you within 24 hours. If you have supporting information, you can optionally share a photo."*
- Worker is NEVER accused. Language is always neutral and supportive.
- If review clears → payout + worker is whitelisted for 60 days (no re-flagging)
- If review confirms fraud → claim denied, account flagged, repeat offenders suspended

#### Key Design Principles:

1. **Never accuse, only verify.** All worker-facing language is neutral. The system "confirms" — it never says "suspicious."
2. **Network drops are expected in storms.** GPS drift and signal loss during actual bad weather is factored into the trust score. A single weak signal is never enough to flag.
3. **First-time benefit of doubt.** A first-time flagged claim with no prior fraud history auto-escalates to Tier 2, never Tier 3 directly.
4. **Transparent timelines.** Workers always know exactly when they'll hear back. No black boxes.
5. **Appeal mechanism.** Every Tier 3 worker can submit one piece of supporting evidence (photo, screenshot of platform showing they were active). Human reviewer must respond within 24 hours.

---

## Tech Stack

### Frontend
*Built as a mobile-first Progressive Web App (PWA) — delivery partners are smartphone-only users and a PWA removes the friction of app store installation while working smoothly on low-end Android devices.*

| Technology | Purpose |
|---|---|
| React.js | Mobile-first PWA — all screens |
| Tailwind CSS | Rapid, consistent styling |
| Framer Motion | Smooth UI animations |
| React Router | Navigation between screens |

### Backend
| Technology | Purpose |
|---|---|
| Python / FastAPI | REST API server, business logic |
| PostgreSQL | Worker profiles, policies, claims |
| FastAPI BackgroundTasks | Scheduled disruption monitoring (Phase 1) |

### AI/ML
| Technology | Purpose |
|---|---|
| Scikit-learn | Risk scoring model (XGBoost Phase 2) |
| Rule engine (Phase 1) | Premium calculation, fraud scoring |
| Pandas + NumPy | Data processing |

### External APIs
| API | Purpose | Phase |
|---|---|---|
| OpenWeatherMap (free tier) | Rainfall, temperature, storm alerts | Phase 1 |
| IQAir / WAQI API (free) | AQI monitoring | Phase 1 |
| Mock civic alert API | Curfew/bandh detection | Phase 1 (mock) |
| Mock Zomato/Swiggy API | Worker activity verification | Phase 1 (mock) |
| Razorpay Test Mode | Payout simulation | Phase 2 |
| Google Maps API | Zone validation, traffic | Phase 2 |

### DevOps
| Technology | Purpose |
|---|---|
| GitHub | Version control, CI/CD |
| Docker | Containerized deployment |
| Render / Railway | Free-tier cloud hosting |

---

## Development Plan

### Phase 1 — Ideation & Foundation (March 4–20) ✅
- [x] Problem research & persona definition
- [x] Workflow design & system architecture
- [x] Weekly premium model design
- [x] Parametric trigger design
- [x] Anti-spoofing architecture
- [x] Tech stack finalization
- [ ] Minimal prototype — onboarding + dashboard + disruption simulation UI

### Phase 2 — Automation & Protection (March 21–April 4)
- [ ] Worker registration & profile system
- [ ] Policy creation with dynamic premium calculation
- [ ] OpenWeatherMap + AQI API integration (live triggers)
- [ ] Mock platform API (worker activity verification)
- [ ] Automated claim initiation pipeline
- [ ] Basic fraud scoring engine (rule-based)
- [ ] Mock payout simulation

### Phase 3 — Scale & Optimise (April 5–17)
- [ ] Advanced multi-signal fraud detection (ML anomaly detection)
- [ ] GPS spoofing detection (WiFi + accelerometer signals)
- [ ] Coordinated ring detection algorithm
- [ ] Razorpay test mode integration (instant payout demo)
- [ ] Worker dashboard (earnings protected, active coverage)
- [ ] Admin/insurer dashboard (loss ratios, predictive analytics)
- [ ] Final demo video + pitch deck

---

## Team

> *(Add your team member names, roles, and college here)*

| Name | Role |
|---|---|
| [Name 1] | Full Stack Development |
| [Name 2] | AI/ML & Backend |
| [Name 3] | UI/UX & Frontend |
| [Name 4] | Research & Documentation |

---

## Why GigShield Wins

1. **Real problem, massive scale** — 11M+ food delivery workers in India with zero income protection
2. **True parametric design** — zero-touch, fully automated, payout in minutes not weeks
3. **Honest about AI** — rule-based in Phase 1, ML-powered in Phase 2/3, no fake claims
4. **Anti-spoofing is genuinely intelligent** — multi-signal, hardware-level detection, not just GPS
5. **Worker-first UX** — no jargon, no paperwork, no accusations, just protection

> *"When the rain stops the city, GigShield starts paying."*

---

*GigShield — Guidewire DEVTrails 2026 | Built with ❤️ for India's gig workers*
