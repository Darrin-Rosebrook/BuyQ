# Architecture

BuyQ is designed as a **modern serverless application** built on Firebase infrastructure with a Next.js frontend.

The architecture separates **user experience, data storage, and background intelligence services** to allow the platform to scale as usage grows.

```
                   ┌───────────────────────┐
                   │        Browser        │
                   │   Next.js / React UI  │
                   └───────────┬───────────┘
                               │
                               ▼
                   ┌───────────────────────┐
                   │ Firebase Authentication│
                   │  User Identity Layer  │
                   └───────────┬───────────┘
                               │
                               ▼
                   ┌───────────────────────┐
                   │     API / Backend     │
                   │ Firebase Cloud Functions │
                   └───────────┬───────────┘
                               │
        ┌──────────────────────┼──────────────────────┐
        ▼                      ▼                      ▼
┌───────────────┐   ┌──────────────────┐   ┌───────────────────┐
│  Cloud Firestore│  │ Price Monitoring │   │ Notification Engine│
│  Application DB │  │ Scheduled Jobs   │   │ Firebase Messaging│
└───────────────┘   └──────────────────┘   └───────────────────┘
```

### Core Components

**Next.js Frontend**

* User dashboard
* Product tracking UI
* Alert configuration

**Firebase Authentication**

* User registration
* Secure login
* Identity management

**Cloud Firestore**

* Wishlist items
* Price history
* Alert rules

**Cloud Functions**

* Product ingestion
* Price monitoring jobs
* Alert evaluation logic

**Firebase Cloud Messaging**

* Real-time push notifications when price conditions are met

---

# Local Development Setup

Follow these steps to run BuyQ locally.

## 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/BuyQ.git
cd BuyQ
```

---

## 2. Install Dependencies

```bash
npm install
```

---

## 3. Configure Firebase

Install the Firebase CLI:

```bash
npm install -g firebase-tools
```

Login to Firebase:

```bash
firebase login
```

Initialize the project:

```bash
firebase use --add
```

---

## 4. Start the Local Development Server

```bash
npm run dev
```

The app will start at:

```
http://localhost:3000
```

---

## 5. Run Firebase Emulators (Optional)

To test backend services locally:

```bash
firebase emulators:start
```

This launches:

* Firestore emulator
* Authentication emulator
* Cloud Functions emulator

---

# Product Roadmap

BuyQ is currently in **MVP development** with a focus on core price monitoring capabilities.

### Phase 1 — MVP (Current)

* User authentication
* Product wishlist
* Price monitoring
* Target price alerts
* Push notifications
* Price history tracking

---

### Phase 2 — Shopping Intelligence

* Promotion signal detection
* Retail sale monitoring
* Promo email filtering
* Improved product metadata extraction

---

### Phase 3 — Advanced Deal Detection

* Coupon stacking engine
* Retailer promotion parsing
* Cashback integrations
* Smart deal scoring

---

### Phase 4 — AI Purchase Advisor

* Price trend prediction
* Best time to buy analysis
* Automated deal discovery
* Personalized shopping recommendations

---

### Phase 5 — Ecosystem Expansion

* Browser extension for one-click product tracking
* Mobile app
* Shared wishlists
* Deal discovery marketplace

---

# Contribution

BuyQ is currently under active development. Contributions, feedback, and ideas are welcome as the platform evolves into a **full shopping intelligence system**.
