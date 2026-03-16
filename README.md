# 🌿 Organic Food — Full-Stack E-commerce Platform

A full-stack e-commerce platform for selling organic food products, featuring a modern customer-facing website and a comprehensive internal admin dashboard.

Built with **React** (frontend) and **Spring Boot** (backend).

---

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Environment Configuration](#environment-configuration)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [License](#license)

---

## ✨ Features

### 🛒 Customer Website

| Feature | Description |
|---|---|
| **Homepage** | Hero image slider, new products, best sellers, and promotional banners |
| **Product Catalog** | Browse by category, view product detail pages with images and key info |
| **Promotions & Sales** | Dedicated sale page showing discounted products and marketing banners |
| **Membership Program** | Register for membership, view membership info and confirmation pages |
| **Online Payment** | Checkout via PayOS with success and failure result pages |
| **Return & Refund** | Page for customers to submit product return requests |
| **Certificates & About** | Display product certifications and brand story |
| **Contact** | Contact information and inquiry form |
| **Authentication** | Sign up, sign in, and forgot password flow with email support |

### 🛠️ Admin Dashboard

#### Overview
- Monthly revenue with a 12-month bar chart
- Key metrics: new customers, monthly revenue, order count
- Recent orders list (customer, order ID, total, status)
- Top-selling products of the current month

#### Management Modules
- **Product Management** — Products, categories, images, suppliers, and certificates
- **Order Management** — View and manage orders and order details
- **Customer Management** — Customer profiles and complaint/feedback handling
- **Voucher & Promotion** — Create and configure vouchers, promotions, and applicable products
- **Inventory & Receipts** — Manage receipts and related inventory data
- **Employee & Permissions** — Employee profiles, roles, and access control
- **System Utilities** — Backup and restore data from the admin panel

---

## 🧰 Tech Stack

### Frontend

| Category | Technologies |
|---|---|
| Core | React 19, TypeScript, Vite |
| UI Libraries | Tailwind CSS, Bootstrap, Ant Design, Ant Design Pro Components |
| Routing & HTTP | React Router, Axios |
| Data & Charts | Recharts |
| UI Extras | Swiper, React Hot Toast, Lucide Icons |

### Backend

| Category | Technologies |
|---|---|
| Core | Spring Boot 3 (Web, Security, Data JPA, Validation, Mail) |
| Security | Spring Security, OAuth2 Resource Server |
| Database | MySQL, JPA / Hibernate |
| Utilities | MapStruct, Lombok |
| Payments | PayOS Java SDK |
| Filtering | springfilter |

---

## 📁 Project Structure

```
organic-food/
├── frontend/                        # React + Vite SPA
│   └── src/
│       ├── pages/
│       │   ├── client/              # Customer-facing pages
│       │   │   ├── home/
│       │   │   ├── product/
│       │   │   ├── product-detail/
│       │   │   ├── sale/
│       │   │   ├── payment/
│       │   │   ├── returns/
│       │   │   ├── certificates/
│       │   │   ├── contact/
│       │   │   ├── about/
│       │   │   ├── membership/
│       │   │   └── vnpay-callback/
│       │   ├── auth/                # Authentication pages
│       │   │   ├── sign-in/
│       │   │   ├── sign-up/
│       │   │   └── forgot-password/
│       │   └── admin/               # Admin dashboard pages
│       │       ├── dashboard/
│       │       ├── products/
│       │       ├── categories/
│       │       ├── orders/
│       │       ├── customers/
│       │       ├── employees/
│       │       ├── suppliers/
│       │       ├── vouchers/
│       │       ├── receipts/
│       │       ├── complaints/
│       │       └── backup-restore/
│       ├── service/                 # API calls and Axios configuration
│       └── utils/                   # Helper functions (formatting, URLs, phone, orders)
│
└── backend/                         # Spring Boot REST API
    └── src/main/java/
        ├── controllers/             # REST endpoints
        ├── services/                # Business logic
        ├── repositories/            # Data access layer
        ├── entities/                # JPA entities
        ├── mappers/                 # MapStruct DTOs
        └── config/                  # Security, payment, mail config
```

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** >= 18.x and **npm** >= 9.x
- **Java** >= 17
- **Maven** >= 3.8
- **MySQL** >= 8.0

---

### Frontend

```bash
# Navigate to the frontend directory
cd frontend

# Install dependencies
npm install

# Start the development server
npm run dev
```

The frontend will be available at `http://localhost:5173` by default.

---

### Backend

```bash
# Navigate to the backend directory
cd backend

# Configure your environment (see Environment Configuration below)

# Run with Maven
mvn spring-boot:run
```

The backend API will be available at `http://localhost:8080` by default.

---

## ⚙️ Environment Configuration

Create or update `backend/src/main/resources/application.yaml` with the following:

```yaml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/organic_food_db
    username: YOUR_DB_USERNAME
    password: YOUR_DB_PASSWORD

  mail:
    host: smtp.gmail.com
    port: 587
    username: YOUR_EMAIL
    password: YOUR_EMAIL_APP_PASSWORD

  payos:
    client-id: YOUR_PAYOS_CLIENT_ID
    api-key: YOUR_PAYOS_API_KEY
    checksum-key: YOUR_PAYOS_CHECKSUM_KEY
```

> ⚠️ Never commit credentials to version control. Use environment variables or a secrets manager in production.

---

## 🔐 Security

- Token-based authentication using **OAuth2 Resource Server**
- **Role-based access control** for admin vs. customer actions via Spring Security
- Password reset flow via **email verification**
- Secure checkout with **PayOS** payment gateways


---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

> Built with ❤️ for a healthier, greener world.
