# Project Overview

This project is a comprehensive e-commerce platform for perfumes, featuring a
SvelteKit frontend and an Express.js backend. The system is architected to be
modular and scalable, providing full transactional capabilities from product browsing
to administrative management. A well-defined RESTful API facilitates all data
interactions between the client and server

# Core Functionalities

## 1- E-commerce & User Interface

The user-facing portion of the application provides a seamless shopping experience.

**ProductCatalog:** Users can browse a comprehensive catalog of perfumes.
The frontend fetches product data from the backend to display a rich
product list.

**ShoppingCart:** The"AddtoCart" functionality allows users to easily manage
selected items before proceeding to a secure checkout. Cart information is
stored in the browser's session storage, eliminating the need for user
authentication to maintain the cart's state during a session.

**Checkout:** Acomplete checkoutworkflow enables customers to finalize
their purchases, which generates a new order record in the backend
database.

## 2- Backend Management & RESTful APIs

The Express.js backend provides a robust set of APIs for all business logic and data
persistence

**Products (4 Endpoints):** A full CRUD (Create, Read, Update, Delete) API
allows for complete management of product inventory.

- **Create:** Addnewperfumeproducts.
- **Read:** Retrieve all products or a single product by ID.
- **Update:** Modifyexisting product details.
- **Delete:** Removeaproduct fromthecatalog.

**Orders (4 Endpoints):** This API manages the order lifecycle.

- **Create:** Registers a newcustomer order.
- **Read:** Retrieves all orders for administrative review.
- **Update:** Allows administrators to change an order's status (e.g., from
  "Processing" to "Shipped").
- **Delete:** Delete selected order

**Contact Messages (3 Endpoints):** This API handles customer communication.

- **Create:** Submitsnewmessagesfrom the contact form.
- **Read:** Providesa list of all messages for administrative review.
- **Delete:** Enables administrators to remove messages.

## 3- Administrative Panel

Adedicated admin panel provides a single interface for managing the entire website.
To access it, navigate to /admin on your domain.

# Technology Stack

- **Frontend:** SvelteKit
- **Backend:** Express.js (Node.js)
- **Database:** SQLite
- **Styling:** Tailwind CSS
- **DataFlow:** All client-server communication is handled via RESTful API calls

# API Endpoints

All API endpoints are prefixed with /api.

## 1- Orders API

- **POST /api/orders:** Creates a new order.
- **GET /api/orders:** Retrieves all orders.
- **PATCH/api/orders/:id/status:** Updates the status of a specific order.
- **Delete /api/orders/delete/:id:** Delete order of selected id.

## 2- Products API

- **POST /api/products:** Creates a new product.
- **GET /api/products:** Retrieves all products.
- **GET /api/products/:id:** Retrieves a single product by ID.
- **PATCH/api/products/:id:** Updates an existing product.
- **DELETE /api/products/:id:** Deletes a product.

## 3- Contact API

- **POST /api/contacts:** Creates a new contact message.
- **GET /api/contacts:** Retrieves all contact messages.
- **GET /api/contacts/:id:** Retrieves a single contact message by ID.
- **DELETE /api/contacts/:id:** Deletes a contact message.

## 4- Admin API

- **POST /api/admin/login:** Authenticates an administrator
