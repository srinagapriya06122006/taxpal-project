# TaxPal 💼📊
### *Personal Finance & Tax Estimator for Freelancers*

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![React](https://img.shields.io/badge/React-18.2-61DAFB?logo=react&logoColor=black)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-7.3-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-18+-339933?logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-5.2-000000?logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose_9-47A248?logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.3-06B6D4?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

**TaxPal** is a full-stack personal finance and tax estimation platform tailored specifically for freelancers, consultants, and independent contractors. It streamlines income and expense tracking, provides category-level budget control with real-time alerts, calculates progressive tax liabilities, monitors advance tax deadlines, and exports financial reports.

---

## ✨ Features

- **💼 Freelance Income & Expense Tracking**
  - Record client payments, freelance projects, recurring bills, and operational expenses.
  - Categorize expenditures (software, travel, equipment, marketing, etc.) with custom notes and timestamps.
  - Filter, search, update, and manage complete transaction histories.

- **📈 Visual Financial Dashboard**
  - Real-time overview of total earnings, total deductions/expenses, and net cash flow.
  - Interactive income vs. expense breakdown charts powered by [Recharts](https://recharts.org/).
  - Monthly reports and dynamic financial health statistics.

- **🎯 Smart Budget Management & Alerts**
  - Set monthly category-specific spending caps.
  - Progress indicators tracking budget consumption.
  - Automated budget warnings and threshold violation alerts.

- **🧮 Progressive Tax Estimation Engine**
  - Calculate estimated tax liability based on multi-tier progressive tax slabs.
  - Factor in deductions and calculate quarterly advance tax liabilities.
  - Store, replace, and review past tax estimates.

- **📅 Interactive Tax Calendar**
  - Visual calendar view ([React Calendar](https://github.com/wojtekmaj/react-calendar)) displaying advance tax installment deadlines.
  - Payment status indicators and timely reminders to prevent penalties.

- **📄 Reports & CSV Data Export**
  - Detailed financial reporting on income, expense distribution, and annual tax obligations.
  - 1-click export of transactions and tax breakdowns to CSV (via `json2csv`) for accounting software or tax accountants.

- **🔐 Robust Security & Authentication**
  - JWT (JSON Web Token) authentication with secure password hashing via `bcryptjs`.
  - Protected client-side routes and backend authorization middleware.
  - API security hardening with [Helmet](https://helmetjs.github.io/) and configurable CORS.

---

## 🛠️ Technology Stack

| Domain | Technology | Description |
| :--- | :--- | :--- |
| **Frontend Framework** | React 18 | Declarative single-page application UI |
| **Build Tool** | Vite | Lightning-fast development and build bundling |
| **Styling** | Tailwind CSS & PostCSS | Modern responsive utility-first styling |
| **Data Visualization** | Recharts | Composable SVG financial charts |
| **Icons** | Lucide React | Clean, lightweight icon suite |
| **HTTP Client** | Axios | REST API client with JWT bearer interceptors |
| **Routing** | React Router DOM v6 | Client-side routing with route guards |
| **Backend Runtime** | Node.js (Express 5) | RESTful API server |
| **Database** | MongoDB & Mongoose | Flexible NoSQL document database and schema modeling |
| **Validation & Security** | Express-Validator & Helmet | Request payload validation and HTTP header protection |
| **Export Utility** | json2csv | Conversion of database collections into CSV spreadsheets |

---

## 📁 Project Structure

```text
-TaxPal-Personal-Finance-Tax-Estimator-for-Freelancers/
├── backend/
│   ├── src/
│   │   ├── controllers/      # Express route controllers (Auth, Budget, Report, Tax, Transaction)
│   │   ├── middleware/       # JWT verification & auth middleware
│   │   ├── models/           # Mongoose schemas (User, Transaction, Budget, TaxEstimate, Report)
│   │   ├── routes/           # RESTful API endpoints
│   │   ├── utils/            # Progressive tax calculation engine
│   │   └── server.js         # Express app initialization and MongoDB connection
│   ├── .env                  # Backend environment configuration
│   └── package.json          # Backend dependencies and scripts
├── frontend/
│   ├── public/               # Public static assets
│   ├── src/
│   │   ├── assets/           # Application icons and branding
│   │   ├── components/       # Reusable UI elements (Navbar, Footer, Hero, Cards, etc.)
│   │   │   └── pages/        # Dashboard, Budget, TaxEstimator, Reports, Login, etc.
│   │   ├── api.js            # Axios client with Authorization header interceptors
│   │   ├── App.jsx           # Application routing and authentication guards
│   │   ├── index.css         # Tailwind base, components, and utilities
│   │   └── main.jsx          # React DOM entry point
│   ├── index.html            # Vite HTML template
│   ├── tailwind.config.js    # Tailwind theme configuration
│   ├── vite.config.js        # Vite configuration
│   └── package.json          # Frontend dependencies and scripts
├── LICENSE                   # MIT License
└── README.md                 # Project documentation
```

---

## 🚀 Getting Started

### Prerequisites

Ensure you have installed:
- [Node.js](https://nodejs.org/) (v18.0.0 or higher recommended)
- [npm](https://www.npmjs.com/) (v9+) or [yarn](https://yarnpkg.com/)
- [MongoDB](https://www.mongodb.com/) (Local service running at `mongodb://127.0.0.1:27017` or a MongoDB Atlas URI)

---

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/-TaxPal-Personal-Finance-Tax-Estimator-for-Freelancers.git
cd -TaxPal-Personal-Finance-Tax-Estimator-for-Freelancers
```

---

### 2. Backend Setup

1. Open a terminal and navigate to the `backend` folder:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create or verify your `.env` file in `backend/.env`:
   ```env
   PORT=5000
   MONGO_URI=mongodb://127.0.0.1:27017/taxpal_db
   JWT_SECRET=your_super_secret_jwt_key
   ```

4. Start the backend development server:
   ```bash
   npm run dev
   ```
   *The server will run on `http://localhost:5000`.*

---

### 3. Frontend Setup

1. Open a second terminal and navigate to the `frontend` folder:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the Vite development server:
   ```bash
   npm run dev
   ```
   *Open your browser and navigate to `http://localhost:5173` (or the URL displayed in the console).*

---

## 📡 REST API Reference

All protected endpoints require an `Authorization: Bearer <TOKEN>` header.

### 🔑 Authentication (`/api/auth`)
| Method | Endpoint | Description | Access |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/auth/register` | Register a new user | Public |
| `POST` | `/api/auth/login` | Authenticate user & retrieve JWT | Public |

### 💳 Transactions (`/api/transactions`)
| Method | Endpoint | Description | Access |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/transactions` | Add a new income or expense transaction | Protected |
| `GET` | `/api/transactions` | Retrieve all user transactions | Protected |
| `GET` | `/api/transactions/summary` | Get financial dashboard summary numbers | Protected |
| `GET` | `/api/transactions/category-breakdown` | Get spending breakdown grouped by category | Protected |
| `GET` | `/api/transactions/monthly-report` | Get monthly revenue vs. expense aggregates | Protected |
| `PUT` | `/api/transactions/:id` | Update transaction by ID | Protected |
| `DELETE`| `/api/transactions/:id` | Delete transaction by ID | Protected |

### 🎯 Budgets (`/api/budgets`)
| Method | Endpoint | Description | Access |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/budgets` | Create category budget | Protected |
| `GET` | `/api/budgets` | Fetch all active budgets | Protected |
| `GET` | `/api/budgets/summary` | Summary of budget allocations and usage | Protected |
| `GET` | `/api/budgets/alerts` | Retrieve alerts for exceeded categories | Protected |
| `GET` | `/api/budgets/:id` | Get specific budget details | Protected |
| `PUT` | `/api/budgets/:id` | Modify budget limit | Protected |
| `DELETE`| `/api/budgets/:id` | Remove a budget | Protected |

### 🧮 Tax Estimation (`/api/tax`)
| Method | Endpoint | Description | Access |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/tax/calculate` | Calculate progressive tax on income/deductions | Protected |
| `PUT` | `/api/tax/replace` | Replace existing tax estimate with updated figure | Protected |
| `POST` | `/api/tax/pay/:id` | Mark tax installment as paid | Protected |
| `GET` | `/api/tax/reminders` | Fetch quarterly tax calendar reminders | Protected |

### 📑 Reports & CSV Exports (`/api/reports`)
| Method | Endpoint | Description | Access |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/reports/income` | Aggregated income report data | Protected |
| `GET` | `/api/reports/expense` | Aggregated expense report data | Protected |
| `GET` | `/api/reports/income-expense` | Comparative income vs expense report | Protected |
| `GET` | `/api/reports/tax` | Historical tax estimation report | Protected |
| `GET` | `/api/reports/income/csv` | Download income records as CSV | Protected |
| `GET` | `/api/reports/expense/csv`| Download expense records as CSV | Protected |
| `GET` | `/api/reports/tax/csv` | Download tax calculation history as CSV | Protected |

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.
