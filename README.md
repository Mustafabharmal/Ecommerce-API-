# 🛒 E-Commerce Platform API

This repository contains a backend application built using Node.js for an e-commerce platform. The project provides a variety of endpoints for user authentication, product management, order processing, and review handling.

## 📚 Table of Contents

- [🔧 Installation](#installation)
- [🚀 Usage](#usage)
- [📋 API Endpoints](#api-endpoints)
- [🏗️ Project Structure](#project-structure)
- [🗂️ Models](#models)
- [📦 Controllers](#controllers)
- [🛠️ Utilities](#utilities)
- [⚠️ Error Handling](#error-handling)
- [📜 License](#license)

## 🔧 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Mustafabharmal/Ecommerce-API-.git
   ```

2. Navigate to the project directory:
   ```bash
   cd Ecommerce-API-
   ```

3. Install the dependencies:
   ```bash
   npm install
   ```

4. Set up environment variables by creating a `.env` file in the root directory and adding the following:
   ```env
   MONGO_URI=your_mongo_db_connection_string
   JWT_SECRET=your_jwt_secret
   JWT_LIFETIME=your_jwt_lifetime
   ```

5. Start the server:
   ```bash
   npm start
   ```

## 🚀 Usage

Once the server is running, you can use tools like Postman or cURL to interact with the API endpoints.

## 📋 API Endpoints

### 🔐 Authentication

- **Register a user**: `POST /api/v1/auth/register`
- **Login a user**: `POST /api/v1/auth/login`
- **Logout a user**: `POST /api/v1/auth/logout`

### 👤 Users

- **Get all users**: `GET /api/v1/users`
- **Get single user**: `GET /api/v1/users/:id`
- **Show current user**: `GET /api/v1/users/showMe`
- **Update user**: `PATCH /api/v1/users/:id`
- **Update user password**: `PATCH /api/v1/users/updateUserPassword`

### 🛍️ Products

- **Create a product**: `POST /api/v1/products`
- **Get all products**: `GET /api/v1/products`
- **Get single product**: `GET /api/v1/products/:id`
- **Update product**: `PATCH /api/v1/products/:id`
- **Delete product**: `DELETE /api/v1/products/:id`
- **Upload product image**: `POST /api/v1/products/uploadImage`

### 📦 Orders

- **Get all orders**: `GET /api/v1/orders`
- **Get single order**: `GET /api/v1/orders/:id`
- **Get current user orders**: `GET /api/v1/orders/showAllMyOrders`
- **Create order**: `POST /api/v1/orders`
- **Update order**: `PATCH /api/v1/orders/:id`

### 📝 Reviews

- **Create review**: `POST /api/v1/reviews`
- **Get all reviews**: `GET /api/v1/reviews`
- **Get single review**: `GET /api/v1/reviews/:id`
- **Update review**: `PATCH /api/v1/reviews/:id`
- **Delete review**: `DELETE /api/v1/reviews/:id`
- **Get reviews for a single product**: `GET /api/v1/reviews/product/:id`

## 🏗️ Project Structure

```
.
├── controllers
│   ├── authController.js
│   ├── orderController.js
│   ├── productController.js
│   ├── reviewController.js
│   └── userController.js
├── models
│   ├── orderModel.js
│   ├── productModel.js
│   ├── reviewModel.js
│   └── userModel.js
├── routes
│   ├── authRoutes.js
│   ├── orderRoutes.js
│   ├── productRoutes.js
│   ├── reviewRoutes.js
│   └── userRoutes.js
├── utils
│   ├── createTokenUser.js
│   ├── attachCookiesToResponse.js
│   ├── checkPermissions.js
│   └── index.js
├── errors
│   ├── CustomError.js
│   ├── BadRequestError.js
│   ├── UnauthorizedError.js
│   └── UnauthenticatedError.js
├── connect.js
├── server.js
└── .env
```

## 🗂️ Models

### User Model (`models/userModel.js`)

Defines the user schema and methods for user data.

### Product Model (`models/productModel.js`)

Defines the product schema, including virtuals for reviews.

### Order Model (`models/orderModel.js`)

Defines the order schema, including order items and user references.

### Review Model (`models/reviewModel.js`)

Defines the review schema, including methods to calculate average ratings.

## 📦 Controllers

### Auth Controller (`controllers/authController.js`)

Handles user registration, login, and logout.

### Order Controller (`controllers/orderController.js`)

Manages order-related operations.

### Product Controller (`controllers/productController.js`)

Handles product creation, retrieval, updating, deletion, and image uploads.

### Review Controller (`controllers/reviewController.js`)

Manages review-related operations.

### User Controller (`controllers/userController.js`)

Handles user-related operations such as getting user details and updating user information.

## 🛠️ Utilities

- **createTokenUser**: Creates a token for user authentication.
- **attachCookiesToResponse**: Attaches JWT to response cookies.
- **checkPermissions**: Checks user permissions for operations.

## ⚠️ Error Handling

Custom error classes are used to handle different types of errors, such as BadRequestError, UnauthorizedError, and UnauthenticatedError.

## 📜 License

This project is licensed under the MIT License.
