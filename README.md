# NextCommerce

A full-stack electronics e-commerce platform built with Next.js, Node.js, Prisma, MySQL, and NextAuth.

The application includes a customer storefront, shopping functionality, authentication, an admin dashboard, and bulk product management using CSV uploads.

---

## Features

### Customer Features

* Browse products by category
* Product details page
* Search and filtering
* Wishlist functionality
* Shopping cart
* Checkout flow
* User authentication

### Admin Features

* Admin dashboard
* Product management
* Bulk product upload using CSV
* Category management
* Order management
* Upload history tracking

---

## Tech Stack

### Frontend

* Next.js 15
* React
* TypeScript
* Tailwind CSS
* DaisyUI
* NextAuth

### Backend

* Node.js
* Express.js
* Prisma ORM

### Database

* MySQL

### Authentication

* NextAuth
* bcryptjs

---

## Project Structure

```text
.
├── app/                  # Next.js App Router
├── components/           # Reusable UI components
├── prisma/               # Prisma schema
├── public/               # Static assets
├── server/               # Express backend API
│   ├── controllers/
│   ├── routes/
│   ├── services/
│   └── prisma/
├── lib/                  # Utilities and API client
└── scripts/              # Helper scripts
```

---

## Prerequisites

Before running the project, install:

* Node.js (v18 or later)
* MySQL Server
* Git

---

## Installation

### 1. Clone Repository

```bash
git clone <repository-url>
cd TechStore-Pro
```

### 2. Install Frontend Dependencies

```bash
npm install
```

### 3. Install Backend Dependencies

```bash
cd server
npm install
cd ..
```

---

## Environment Variables

Create a `.env` file in the root directory:

```env
DATABASE_URL="mysql://root:YOUR_PASSWORD@localhost:3306/ecommerce_db"

NEXTAUTH_URL="http://localhost:3000"
NEXTAUTH_SECRET="your-secret-key"

NEXT_PUBLIC_API_BASE_URL="http://localhost:3001"
```

Create another `.env` file inside the `server` directory:

```env
DATABASE_URL="mysql://root:YOUR_PASSWORD@localhost:3306/ecommerce_db"
```

---

## Database Setup

### Generate Prisma Client

Root project:

```bash
npx prisma generate
```

Backend:

```bash
cd server
npx prisma generate
```

### Push Database Schema

```bash
npx prisma db push
```

---

## Create Default Categories

Inside the server folder:

```bash
node scripts/create-default-categories.js
```

---

## Create Admin User

```bash
node createAdminUser.js admin@example.com Admin123
```

---

## Run the Application

### Start Backend

```bash
cd server
npm start
```

Backend runs on:

```text
http://localhost:3001
```

### Start Frontend

```bash
npm run dev
```

Frontend runs on:

```text
http://localhost:3000
```

---

## Import Sample Products

1. Login as admin
2. Navigate to:

```text
http://localhost:3000/admin/bulk-upload
```

3. Upload:

```text
bulk-upload-example.csv
```

Products will automatically appear on the storefront.

---

## API Example

Get all products:

```http
GET /api/products
```

Example:

```json
[
  {
    "title": "Samsung Galaxy S24 Ultra",
    "price": 1299
  }
]
```

---

## Future Improvements

* Payment gateway integration
* Product reviews
* Inventory analytics
* Email notifications
* Docker support
* CI/CD deployment pipeline

---

## Author

Suraj Jha

Built as a full-stack e-commerce project using Next.js, Node.js, Prisma, and MySQL.
