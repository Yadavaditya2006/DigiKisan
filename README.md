# DigiKisan — Extended Description (Point-Wise)

---

## 1. Project Overview
- **DigiKisan** is a smart Android mobile application built to assist farmers in Maharashtra, India.
- It digitizes key agricultural workflows — from crop management to market intelligence — into one unified, offline-capable platform.
- The app is designed for rural usability with multilingual support and a clean, intuitive interface.

## 2. Secure Authentication System
- Farmers register using their full name, mobile number, password, district, and taluka.
- Passwords are securely hashed using **SHA-256 with a unique random salt** per user — plain-text passwords are never stored.
- **Duplicate registration detection** prevents the same mobile number from being registered twice.
- A **Forgot Password** flow allows users to recover their account by verifying their registered mobile number and setting a new password.
- Login validates credentials against the hashed password stored in the local SQLite database.

## 3. APMC Market Price Tracker
- Displays **real-time commodity pricing** data from Agricultural Produce Market Committees (APMCs) across Maharashtra.
- Farmers can browse prices by **division, district, and market name**.
- Each listing shows **minimum, maximum, and modal prices** along with arrival quantities.
- A **price trend indicator** (rising/falling/stable) helps farmers decide the best time and place to sell.
- Detailed market view includes **trend explanations** and historical comparison with previous modal prices.

## 4. Crop Assessment Engine
- Allows farmers to evaluate their **crop health** by providing inputs such as:
  - Crop name and growth stage
  - Irrigation method and watering interval
  - Soil type
  - Waterlogging observations
  - Visible pest/disease symptoms
- The engine generates a **comprehensive assessment report** that includes:
  - Assessment category (Healthy / Moderate Risk / High Risk)
  - Supporting factors and risk factors
  - Suggested corrective actions
  - Precautionary measures

## 5. Farm Diary & Financial Tracking
- Farmers can maintain a **daily log of farming activities** such as sowing, fertilizing, pesticide spraying, irrigation, and harvesting.
- Each diary entry records:
  - Activity type and date
  - Descriptive notes
  - **Expense amount** and **income amount**
- This helps farmers track their **farm-level profit and loss** over time.

## 6. Government Schemes Directory
- Provides a curated list of **central and state government agricultural schemes**.
- Each scheme entry includes:
  - Scheme name and issuing authority
  - Category and objective
  - Benefits summary
  - Eligibility criteria
  - Required documents
  - Step-by-step application process
  - Official portal URL and helpline contact
- Farmers can **save schemes** for quick access later.

## 7. Farmer Profile Management
- Each farmer can create and manage a detailed **farm profile** including:
  - Primary crop and crop variety
  - Sowing date
  - Land area (in acres)
  - Soil type
  - Irrigation method and watering schedule
- This profile is used to personalize recommendations across the app.

## 8. AI Chatbot for Agricultural Guidance
- An in-app **chatbot interface** provides conversational assistance to farmers.
- Farmers can ask questions related to farming practices, pest control, crop care, and more.
- Designed to offer quick, accessible guidance without needing internet-based search.

## 9. Weather Reports
- Displays **weather information** relevant to the farmer's location.
- Helps farmers plan sowing, irrigation, and harvesting activities based on current and forecasted conditions.

## 10. Learning Resources
- Provides **educational content and best practices** on modern farming techniques.
- Serves as a knowledge base for farmers to learn about crop management, soil health, pest control, and sustainable agriculture.

## 11. Multilingual Support
- Full app interface available in **three languages**:
  - **Marathi** (मराठी) — primary language for Maharashtra farmers
  - **Hindi** (हिंदी)
  - **English**
- Language preference is stored per user and applied across all screens.

## 12. Offline-First Architecture
- All data is stored locally using **SQLite** — the app works **fully offline** without internet.
- Critical for farmers in rural areas with limited or unreliable network connectivity.
- Database uses **Write-Ahead Logging (WAL)** for efficient concurrent access.

## 13. Technology Stack
- **Language**: Java
- **UI**: XML Layouts with Material Design components
- **Database**: SQLite via `SQLiteOpenHelper`
- **Security**: SHA-256 password hashing with per-user salt (`SecurityUtils`)
- **Session Management**: SharedPreferences-based (`UserSessionManager`)
- **Notifications**: Android `NotificationHelper` with farm activity reminders
- **Architecture**: Singleton DatabaseHelper pattern, modular Activity-based navigation

## 14. Target Users
- Small and marginal farmers in Maharashtra, India
- Agricultural advisors and extension workers
- Rural entrepreneurs involved in crop trading

---
