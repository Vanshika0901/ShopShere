A complete microservices-based e-commerce project built using .NET 6 Web API and MVC, following industry standards with authentication, messaging, API Gateway, and a full MVC UI.

 **Project Overview
 
Services included:**
AuthAPI → User registration & login

ProductAPI → Products and categories

ShoppingCartAPI → Add, edit, remove items + apply discount codes

CouponAPI → CRUD operations on coupons

OrderAPI → Saving orders and viewing order details

PaymentAPI → Process payments

RewardAPI → User rewards & points system

EmailAPI → Sending order confirmation emails

API Gateway using Ocelot to route calls from UI to microservices

MVC Web UI as front-end client for shopping flow

Asynchronous messaging between services via RabbitMQ or Azure Service Bus

JWT-based authentication & role-based authorization

🧱 **Architecture & Folder Structure**

Mango.GatewaySolution/ → Ocelot API Gateway

Mango.MessageBus/ → Shared messaging utilities

Mango.Services.* → Individual service projects (Auth, Cart, Coupon, Order, Payment, Product, Reward, Email)

Mango.Web/ → MVC application with Razor views and front-end UI

Mango.sln → Visual Studio solution to run all services

🛠 **Tech Stack**

Component	Technologies Used
Web APIs	ASP.NET Core Web API (.NET 6)
UI	ASP.NET Core MVC (Razor pages, Bootstrap UI)
Auth & Security	JWT Token, ASP.NET Identity
Messaging	RabbitMQ or Azure Service Bus
Gateway	Ocelot API Gateway
Databases	SQL Server / MongoDB
Communication	Synchronous REST + (optional) gRPC between services
Containerization	Docker Compose (for RabbitMQ, databases, etc.)
CI/CD & Deployment	Optional Dockerized setup

🧭 **Features**

Modular microservices architecture – each service runs independently

Authentication & Authorization using JWT tokens via AuthAPI

Cart, Coupon, Order workflows with message-driven integration

Payment processing and email service for real order workflow

Interactive MVC UI connecting to gateway & APIs

Flexible messaging with RabbitMQ or Azure Service Bus

API Gateway handling routing, routing versioning, and security

🧪 **Getting Started

Prerequisites**

.NET 6 SDK or higher installed

Visual Studio 2022 / VS Code

Docker (for RabbitMQ and optional Mongo/SQL containers)

Connection strings configured in each service appsettings.json

Setup Steps
Clone the repo

bash
Copy
Edit
git clone https://github.com/Vanshika0901/ShopShere
cd Mango_Microservices
Run RabbitMQ via Docker (if not using Azure Service Bus)

bash
Copy
Edit
Open Mango.sln in Visual Studio or via CLI

Run each service project individually

Launch MVC UI (Mango.Web)

This will host the storefront, allowing you to browse products, create account, add to cart, checkout, etc.

API Gateway (Mango.GatewaySolution) should be configured to route to each service endpoint and apply authentication logic.

🧠 **API Usage (via API Gateway)**

POST /api/auth/login → Get JWT token

GET /api/products → List of products (public)

POST /api/cart → Add item (authenticated user)

POST /api/order → Checkout cart

POST /api/payment → Process payment

POST /api/email/send → Send confirmation email

Note: Actual paths may differ by service. Please check each service's appsettings.json or swagger docs.
