<div align="center">

<img src="https://img.shields.io/badge/MERN-Stack-61DAFB?style=for-the-badge&logo=react&logoColor=white" />
<img src="https://img.shields.io/badge/MongoDB-Atlas-47A248?style=for-the-badge&logo=mongodb&logoColor=white" />
<img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white" />
<img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" />
<img src="https://img.shields.io/badge/JWT-Auth-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white" />

<br /><br />

# 📈 StockX — Full-Stack Stock Trading Platform

**A Zerodha-inspired, high-performance trading ecosystem built for seamless financial experiences.**

## 📌 Table of Contents

- [About the Project](#-about-the-project)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [API Reference](#-api-reference)
- [Roadmap](#-roadmap)
- [Author](#-author)


## 🧠 About the Project

**StockX** is a full-stack stock trading simulation platform inspired by **Zerodha Kite** — one of India's most popular trading platforms. It is designed to bridge the gap between complex financial market data and an intuitive, real-world user experience.

Whether you're learning how stock markets work or building a portfolio tracker prototype, StockX gives you a clean, distraction-free interface backed by a robust MERN stack architecture.

> 💡 *This is a simulation platform — no real money is involved. All trades and balances are virtual.*


## ✨ Features

### 🎨 UI/UX
- **Kite-Inspired Interface** — Clean, white-and-blue aesthetic with optional dark mode
- **Fully Responsive** — Optimized for Mobile, Tablet, and Desktop
- **Interactive Charts** — Real-time data visualization via Chart.js / Recharts
- **Micro-interactions** — Smooth transitions, hover effects, and animated feedback

## Systen Design Diagram

                    ┌───────────────────────────┐
                    │        User (Browser)     │
                    │  (React Frontend UI)      │
                    └────────────┬──────────────┘
                                 │
                                 ▼
                    ┌───────────────────────────┐
                    │       Frontend Layer      │
                    │ React / Next.js UI        │
                    │ - Dashboard               │
                    │ - Charts                 │
                    │ - Portfolio              │
                    └────────────┬──────────────┘
                                 │ REST API Calls
                                 ▼
                    ┌───────────────────────────┐
                    │        API Gateway        │
                    │   (Express / Django)      │
                    └────────────┬──────────────┘
                                 │
         ┌───────────────────────┼────────────────────────┐
         ▼                       ▼                        ▼
┌──────────────────┐   ┌────────────────────┐   ┌────────────────────┐
│ Auth Service     │   │ Trading Service    │   │ Market Data Service│
│ - Login/Register │   │ - Buy/Sell Stocks  │   │ - Stock Prices     │
│ - JWT Tokens     │   │ - Order Mgmt       │   │ - Charts API       │
└─────────┬────────┘   └─────────┬──────────┘   └─────────┬──────────┘
          │                      │                        │
          ▼                      ▼                        ▼
   ┌──────────────┐     ┌──────────────┐        ┌──────────────────┐
   │ User DB      │     │ Orders DB    │        │ External APIs    │
   │ (MongoDB /   │     │ (Trades,     │        │ (IEX, Yahoo,     │
   │ PostgreSQL)  │     │ Portfolio)   │        │ News API etc.)   │
   └──────────────┘     └──────────────┘        └──────────────────┘

                                 │
                                 ▼
                    ┌───────────────────────────┐
                    │   Cache / Realtime Layer  │
                    │   (Redis / WebSocket)     │
                    └───────────────────────────┘

### ⚙️ Core Functionalities

| Feature | Description |
|---|---|
| 📊 **Market Watchlist** | Add/remove stocks to monitor real-time price movements |
| 🛒 **Order Execution** | Simulate Market and Limit orders for buying/selling |
| 💼 **Portfolio Management** | Track holdings, average buy price, and live P&L |
| 💰 **Funds Portal** | Manage virtual balance to simulate real-world trading |
| 🔐 **Secure Auth** | JWT-based authentication with protected API routes |
| 📱 **Responsive Design** | Seamless experience across all screen sizes |


## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React.js, Tailwind CSS, Material UI |
| **State Management** | Redux Toolkit / Context API |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB Atlas |
| **Authentication** | JSON Web Tokens (JWT) |
| **Charts** | Chart.js / Recharts |
| **Icons** | Lucide React, FontAwesome |


## 📁 Project Structure

```
Building-a-Stock-Trading-Platform/
│
├── Backend/
│   ├── models/
│   │   ├── User.js          # User schema
│   │   ├── Holdings.js      # Portfolio/holdings schema
│   │   └── Orders.js        # Order history schema
│   ├── routes/
│   │   ├── auth.js          # Login/Register routes
│   │   ├── holdings.js      # Portfolio routes
│   │   └── orders.js        # Order execution routes
│   └── index.js             # Express server entry point
│
├── frontend/
│   ├── public/
│   └── src/
│       ├── components/
│       │   ├── Watchlist.jsx
│       │   ├── Dashboard.jsx
│       │   └── OrderWindow.jsx
│       ├── pages/
│       │   ├── Home.jsx
│       │   ├── Holdings.jsx
│       │   └── Funds.jsx
│       ├── store/           # Redux / Context state logic
│       └── App.js
│
├── Dashboard/
│   └── node_modules/
│
└── README.md


## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- [Node.js](https://nodejs.org/) (v18+)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- [MongoDB Atlas](https://www.mongodb.com/atlas) account

### 1. Clone the Repository

```bash
git clone https://github.com/Umangi-webdev/Building-a-Stock-Trading-Platform.git
cd Building-a-Stock-Trading-Platform
```

### 2. Setup the Backend

```bash
cd Backend
npm install
```

Create a `.env` file in the `Backend/` directory (see [Environment Variables](#-environment-variables)).

```bash
npm start
# Server runs on http://localhost:5000
```

### 3. Setup the Frontend

```bash
cd ../frontend
npm install
npm start
# App runs on http://localhost:3000

## 🔑 Environment Variables

Create a `.env` file in the `Backend/` directory and add the following:

```env
MONGO_URI=your_mongodb_atlas_connection_string
JWT_SECRET=your_secret_key
PORT=5000

> ⚠️ Never commit your `.env` file. It is already listed in `.gitignore`.


## 📡 API Reference

### Auth Routes

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/auth/register` | Register a new user |
| `POST` | `/api/auth/login` | Login and get JWT token |

### Holdings Routes *(Protected)*

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/holdings` | Get all holdings for the user |
| `POST` | `/api/holdings` | Add a new holding |

### Orders Routes *(Protected)*

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/orders` | Get order history |
| `POST` | `/api/orders` | Place a new order |

> 🔐 Protected routes require a valid JWT in the `Authorization: Bearer <token>` header.

## 🗺 Roadmap

- [x] JWT Authentication
- [x] Market Watchlist
- [x] Order Execution (Market & Limit)
- [x] Portfolio P&L Tracking
- [x] Funds Management
- [ ] Live Stock Price API Integration
- [ ] WebSocket for real-time price updates
- [ ] Paper Trading Mode
- [ ] Email Notifications for Orders
- [ ] Admin Analytics Dashboard


## 👩‍💻 Author

**Umangi Patel**

- 🎓 Computer Engineering @ GEC Palanpur — **9.35 SPI**
- 💡 Expertise: MERN Stack | Dart | AI/ML
- 🔗 [LinkedIn] https://www.linkedin.com/in/gj-cp-gecpl-2027-037-umangi?utm_source=share_via&utm_content=profile&utm_medium=member_android
- 🐙 [GitHub](https://github.com/Umangi-webdev)


<div align="center">

⭐ If you found this project helpful, please give it a **star** on GitHub!

Made with ❤️ by [Umangi Patel](https://github.com/Umangi-webdev)

</div>
