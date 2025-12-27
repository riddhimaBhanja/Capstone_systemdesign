

#  Loan Management System (LMS)

**Enterprise-Grade Secure Full-Stack Web Application**  
Built with **Spring Boot & Angular** following **Microservices Architecture**

---

##  Project Overview

The **Loan Management System (LMS)** is a production-ready, cloud-deployable enterprise application designed to **digitize and automate the complete loan lifecycle** for banks, NBFCs, and financial institutions.

This system replaces manual and semi-automated workflows with a **secure, scalable, API-driven platform**, ensuring transparency, accuracy, and auditability across all loan operations.

---

##  Business Objectives

The primary goals of this system are to:

-  Automate the end-to-end loan lifecycle
-  Accelerate loan application and approval processes
-  Ensure transparent approval workflows
-  Accurately calculate and track EMIs
-  Secure sensitive customer financial data
-  Provide real-time dashboards and reports
-  Support cloud-ready, scalable deployment

---

##  High-Level Features

-  **Multi-Role Access Control**
  - Admin
  - Loan Officer
  - Customer

-  Online loan application and real-time status tracking  
-  Configurable loan types, interest rates, and tenures  
-  Automated EMI schedule generation  
-  EMI repayment and overdue tracking  
-  JWT-based authentication and role-based authorization  
-  Reporting and dashboard analytics  
-  Production-ready REST APIs  

---

## System Architecture

The system follows a **Microservices-Oriented Architecture** combined with **Layered Design Principles**.

### Architectural Highlights

- Loose coupling between services  
- Independent data ownership per service  
- Stateless backend services  
- REST-based inter-service communication  
- SPA (Angular) frontend with secured APIs  
- Event-driven communication using message broker  

---

##  Core System Components

### 1️⃣ Frontend Layer
- Angular Single Page Application (SPA)
- Handles UI rendering, validations, and role-based navigation
- Communicates via secured REST APIs

### 2️⃣ Backend Layer
- Spring Boot microservices
- Implements business logic, validations, workflows, and security
- Exposes versioned REST APIs

### 3️⃣ Persistence Layer
- Independent database per microservice
- Ensures data isolation and scalability

### 4️⃣ Security Layer
- JWT authentication
- Role-Based Access Control (RBAC)
- Encrypted password storage
- Secured API endpoints

---

##  Technology Stack

###  Backend
- Java 17+
- Spring Boot 3.x
- Spring Web (REST APIs)
- Spring Data JPA & Hibernate
- Spring Security with JWT
- Swagger / OpenAPI
- Maven

###  Frontend
- Angular (Latest)
- TypeScript
- Angular Material / Bootstrap
- Reactive Forms
- HTTP Interceptors & Route Guards

###  Database
- MySQL / PostgreSQL
- Separate schema per microservice

### ⚙️ DevOps & Tools
- Git & GitHub
- Postman
- Environment-based configuration (Dev / Test / Prod)

###  Testing
- JUnit 5
- Mockito
- Postman API Collections

---

##  Microservices Overview

| Service Name              | Responsibility                                      | Database |
|---------------------------|----------------------------------------------------|----------|
| Identity Service          | Authentication, JWT, roles                         | identity_db |
| Customer Profile Service  | Profile & KYC management                           | profile_db |
| Loan Application Service  | Loan submission & tracking                         | loan_application_db |
| Loan Processing Service   | Loan approval, EMI calculation                     | loan_processing_db |
| Repayment Service         | EMI schedule, payments, closure                    | repayment_db |
| Notification Service      | Email & system notifications                      | notification_db |
| Config Service            | Centralized configuration                          | No DB |
| Eureka Service            | Service discovery                                  | No DB |
| API Gateway               | Routing, security, RBAC enforcement                | No DB |

---

##  API Design & Endpoints

### Authentication APIs
```

POST /api/auth/register
POST /api/auth/login
GET  /api/auth/validate

```

### Loan Application APIs
```

POST /api/loan-applications/apply
GET  /api/loan-applications/my
PUT  /api/loan-applications/{id}/review

```

### Loan Processing APIs
```

POST /api/loans/{applicationId}/approve
POST /api/loans/{applicationId}/reject
GET  /api/loans/{loanId}

```

### Repayment APIs
```

GET  /api/repayments/loan/{loanId}
POST /api/repayments/emi/{emiId}/pay
GET  /api/repayments/history/{loanId}
GET  /api/repayments/overdue

```

---

##  Business Rules

###  Loan Application Rules
- Customer must be registered and verified
- Only **one active loan per loan type** is allowed
- Loan amount must be within predefined limits
- Loan tenure must be selected from fixed options
- Loan application cannot be edited after submission

###  Loan Approval Rules
- Only **Loan Officers** can approve or reject loans
- Approval depends on:
  - Credit score
  - Income eligibility
  - Existing liabilities
- Rejection reason must be stored

### Post-Approval Actions
- EMI schedule generated automatically
- Customer notified with loan and EMI details
- Loan lifecycle tracking begins

---

##  Error Handling Strategy

- Centralized exception handling using `@ControllerAdvice`
- Custom exceptions:
  - ResourceNotFoundException
  - ValidationException
  - UnauthorizedAccessException
- Standardized error response format:
  - Timestamp
  - Status
  - Error code
  - Message
  - Path

---

## Security Design

- JWT-based stateless authentication
- Role-based access control (RBAC)
- BCrypt password hashing
- Method-level security
- HTTP interceptors for token propagation

---

##  Non-Functional Requirements

- **Scalability:** Horizontally scalable microservices
- **Security:** Encrypted credentials and secured APIs
- **Performance:** Optimized queries & pagination
- **Maintainability:** Clean layered architecture
- **Availability:** Fault-tolerant stateless services
- **Auditability:** Complete loan lifecycle traceability

---

##  Testing Strategy

###  Unit Testing
- JUnit & Mockito
- Mocked repositories and services

###  API Testing
- Postman collections
- Authentication & authorization scenarios

###  Validation & Security Testing
- Input validation
- Unauthorized access tests
- Token expiry handling

---

##  Conclusion

The **Loan Management System** demonstrates **enterprise-level system design**, **secure full-stack development**, and **real-world financial workflows**.

It is **production-ready**, **cloud-deployable**, and built using **industry best practices**, making it a strong representation of modern backend and frontend engineering capabilities.

---
```

---

