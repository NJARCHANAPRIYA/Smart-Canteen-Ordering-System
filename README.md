# Smart Canteen Ordering System

## Features
- Menu item listing and admin menu creation
- Place an order with quantity and automatic total calculation
- Track orders and update status: PLACED, PREPARING, READY, COMPLETED, CANCELLED
- PostgreSQL persistence and responsive browser interface

## Requirements
Java 17+, PostgreSQL, Maven.

## Setup
Create a database:
```sql
CREATE DATABASE canteen_db;
```
Default DB is `canteen_db`, username `postgres`, password `postgres`. Set environment variables `DB_URL`, `DB_USERNAME`, and `DB_PASSWORD` to override. Change defaults for your own computer.

Run:
```bash
mvn spring-boot:run
```
Open `http://localhost:8081`.

## First use
1. Add a menu item in the Admin section.
2. Choose the item, enter a customer name and quantity, and place an order.
3. Change the order status from the Orders table.

## API
- `GET /api/menu`
- `POST /api/admin/menu`
- `POST /api/orders`
- `GET /api/orders`
- `GET /api/orders/{id}`
- `PATCH /api/admin/orders/{id}/status`

## Important security note
This is a learning prototype. Admin routes are not protected by authentication, and payment integration is not included. Do not use it for a real canteen without adding authentication, authorization, tests, and production configuration.
