# Project Requirement Document (PRD)

## Project Name
Annan Tracker

## Overview
The Annan Tracker is a Spring Boot application designed to help users manage their finances in ZL currency. The application allows users to add money, record daily expenditures by category, track price changes for products, and generate monthly expenditure summaries. It uses an in-memory database for data storage and includes Swagger-first API documentation for easy API exploration.

---

## Features

### 1. **User Account Management**
- My Dashboard:
  - Show the current month's expenditure.
  - Highlight any price variation found for any product bought on different days or times.
- Add money to the account.
- View the current available balance.

### 2. **Expenditure Tracking**
- Record daily expenditures by category:
  - Groceries
  - Shopping
  - Bills
- Track price changes for products:
  - Notify if the same product is bought at a cheaper or higher price.

### 3. **Expenditure Summaries**
- Generate monthly expenditure summaries:
  - Total expenditure per category.
  - Total expenditure for the month.
  - Highlight the category with the most expenditure.

### 4. **View Balance**
- Fetch the current available balance.
- Alert if the balance is low (< 250 ZL).

### 5. **API Documentation**
- Swagger-first OpenAPI documentation for all endpoints.

---

## Functional Requirements

### 1. **Add Money**
- Endpoint to add money to the user's account.
- Validate that the amount is positive.

### 2. **Record Expenditure**
- Endpoint to record an expenditure with the following details:
  - Product name
  - Category
  - Price
  - Date
- Check if the product price has increased or decreased compared to previous purchases.

### 3. **View Balance**
- Endpoint to fetch the current available balance.
- Alert if the balance is low (< 250 ZL).

### 4. **Generate Monthly Summary**
- Endpoint to generate a summary of expenditures for a given month:
  - Total expenditure per category.
  - Total expenditure for the month.
  - Highlight the category with the most expenditure.

### 5. **My Dashboard**
- Endpoint to fetch the current month's expenditure.
- Highlight any price variation found for any product bought on different days or times.

### 6. **Swagger Integration**
- Define API endpoints and specifications in the OpenAPI documentation first.
- Generate controllers and DTOs from the OpenAPI specification.

---

## Non-Functional Requirements
- Use an in-memory database (e.g., H2) for data storage.
- Ensure the application is lightweight and responsive.
- Follow RESTful API design principles.
- Include proper error handling and validation.

---

## Technology Stack
- **Backend**: Java 21, Spring Boot 4
- **Database**: H2 (In-Memory Database)
- **API Documentation**: Swagger-first OpenAPI

---

## API Endpoints

### 1. **Add Money**
- **POST** `/api/balance/add`
- Request Body: `{ "amount": 100.0 }`

### 2. **Record Expenditure**
- **POST** `/api/expenditure/add`
- Request Body: `{ "productName": "Milk", "category": "Groceries", "price": 5.0, "date": "2023-10-01" }`

### 3. **View Balance**
- **GET** `/api/balance`
- Alert if balance is low (< 250 ZL).

### 4. **Generate Monthly Summary**
- **GET** `/api/expenditure/summary?month=10&year=2023`
- Highlight the category with the most expenditure.

### 5. **My Dashboard**
- **GET** `/api/dashboard`
- Show the current month's expenditure.
- Highlight any price variation found for any product bought on different days or times.

### 6. **Swagger UI**
- **GET** `/swagger-ui.html`

---

## Future Enhancements
- Add user authentication and authorization.
- Support for persistent database storage.
- Add notifications for budget limits.
- Support for multiple currencies.

---

## Assumptions
- The application will only support ZL currency in the first phase.
- The in-memory database will reset on application restart.
- No user authentication is required in the first phase.

---

## Deliverables
- Spring Boot application source code.
- Swagger-first OpenAPI documentation.
- Unit and integration tests.