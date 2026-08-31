# Implementation Plan

## Project Name
Annan Tracker

## Overview
This document outlines the step-by-step implementation plan for the Annan Tracker project. The project will be developed in stages to ensure a structured and efficient development process.

---

## Stage 1: Project Setup
### Tasks:
1. Initialize a Spring Boot project using Java 21 and Spring Boot 4.
2. Configure the project dependencies:
   - Add H2 in-memory database.
   - Add OpenAPI dependencies for API documentation.
   - Add Lombok for reducing boilerplate code.
   - Add a mapper library (e.g., MapStruct) for mapping DTOs and DAOs.
3. Set up the project structure:
   - Create packages for `controller`, `service`, `repository`, `model`, `dto`, and `exception`.
4. Implement a global exception handling mechanism:
   - Use `@ControllerAdvice` to handle exceptions globally.
   - Return appropriate HTTP status codes for different exceptions.
5. Create a basic `application.yaml` configuration file.
6. Use a Swagger-first approach:
   - Define the API endpoints and their specifications in the OpenAPI documentation first.
   - Generate the controllers and DTOs from the OpenAPI specification.

### Deliverables:
- Basic project structure with dependencies configured.
- Application runs successfully with a "Hello World" endpoint.
- Proper exception handling with HTTP status codes.
- OpenAPI specification file defining all endpoints.

---

## Stage 2: User Account Management
### Tasks:
1. Implement the "Add Money" feature:
   - Create an endpoint to add money to the user's account.
   - Validate that the amount is positive.
2. Implement the "View Balance" feature:
   - Create an endpoint to fetch the current available balance.
   - Add an alert if the balance is below 250 ZL.
3. Implement "My Dashboard":
   - Create an endpoint to show the current month's expenditure.
   - Highlight any price variation for products bought on different days or times.

### Deliverables:
- Fully functional User Account Management module.
- Unit tests for all endpoints.

---

## Stage 3: Expenditure Tracking
### Tasks:
1. Implement the "Record Expenditure" feature:
   - Create an endpoint to record daily expenditures with details (product name, category, price, date).
   - Track price changes for products and notify if the price has increased or decreased.
2. Categorize expenditures into "Groceries", "Shopping", and "Bills".
3. Use DTOs for input and output, and map them to DAOs using the mapper library.

### Deliverables:
- Fully functional Expenditure Tracking module.
- Unit tests for all endpoints.

---

## Stage 4: Expenditure Summaries
### Tasks:
1. Implement the "Generate Monthly Summary" feature:
   - Create an endpoint to generate a summary of expenditures for a given month.
   - Calculate total expenditure per category and for the month.
   - Highlight the category with the most expenditure.
2. Use DTOs for output and map them from DAOs using the mapper library.

### Deliverables:
- Fully functional Expenditure Summaries module.
- Unit tests for all endpoints.

---

## Stage 5: API Documentation
### Tasks:
1. Integrate OpenAPI for API documentation.
2. Document all endpoints with request and response details.
3. Test the OpenAPI documentation using Swagger UI.

### Deliverables:
- Complete API documentation accessible via Swagger UI.

---

## Stage 6: Testing and Validation
### Tasks:
1. Write integration tests for all modules.
2. Perform end-to-end testing of the application.
3. Validate the application against the requirements in the PRD.

### Deliverables:
- Comprehensive test coverage.
- Bug-free and validated application.

---

## Stage 7: Deployment
### Tasks:
1. Package the application as a JAR file.
2. Deploy the application to a local or cloud environment.
3. Provide deployment instructions.

### Deliverables:
- Deployed application ready for use.
- Deployment documentation.

---

## Future Enhancements
1. Add user authentication and authorization.
2. Support for persistent database storage.
3. Add notifications for budget limits.
4. Support for multiple currencies.
5. Extend the API for mobile application integration.

---

## Timeline
| Stage                | Estimated Time |
|----------------------|----------------|
| Stage 1: Project Setup | 2 days         |
| Stage 2: User Account Management | 4 days         |
| Stage 3: Expenditure Tracking | 4 days         |
| Stage 4: Expenditure Summaries | 3 days         |
| Stage 5: API Documentation | 2 days         |
| Stage 6: Testing and Validation | 3 days         |
| Stage 7: Deployment | 1 day          |

---

## Conclusion
This implementation plan provides a clear roadmap for developing the Annan Tracker project in a structured and efficient manner. Each stage builds upon the previous one, ensuring a robust and feature-complete application.
