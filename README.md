# 🏦 Fidelity Investment Inc. | Private Wealth Portal
**Secure Portfolio Management System for High-Net-Worth Individuals**

## 📊 Executive Summary
This project is a full-stack financial dashboard designed to provide real-time wealth analytics and secure transaction management. It is currently configured for a principal client with a diversified portfolio.

* **Principal Client:** Chase Rice
* **Current Portfolio Value:** $6,080,333.42
* **Account Tier:** Diamond Infinite (Private Wealth)
* **Audit Period:** January 2023 – March 2026

---

## 🚀 Technical Architecture
The portal leverages a modern, cloud-native stack to ensure 99.9% uptime and ACID-compliant financial data:

* **Frontend:** Responsive UI built with HTML5, CSS3, and JavaScript (ES6+), optimized for mobile banking.
* **Backend & Database:** Powered by **Google Cloud Firestore** (Native Mode) for real-time data synchronization.
* **Automation:** **GitHub Actions** workflows for automated daily portfolio appreciation and interest credits.
* **Data Visualization:** **Chart.js** integration for tracking investment growth and asset allocation.
* **Security:** Firebase Authentication with secure Environment Variables for API protection.

---

## 🛡️ Security & Integrity
To protect the **$6.08M** AUM (Assets Under Management), the system implements:
1.  **Strict Firestore Rules:** Only authenticated UIDs can access specific document paths.
2.  **Encrypted Ledger:** Transaction history is stored in an immutable array to prevent data tampering.
3.  **Scheduled Updates:** A secure Cron Job updates balances at 00:00 UTC without manual intervention.

---

## 🛠️ Key Functionalities
* **Live Wealth Tracker:** Dynamic display of net worth and daily market gains.
* **Transaction Ledger:** A comprehensive history of credits (dividends) and debits (luxury transfers) since 2023.
* **Internal Transfers:** Integrated logic to perform real-time balance deductions.
* **Investment Analytics:** Doughnut charts showing the split between Stocks, Cash, and Bonds.

---

## 📈 Deployment
This project is deployed using **Firebase Hosting** and is integrated with a custom domain for a professional client-facing experience.
