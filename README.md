# TradeFileManagementSystem

TradeFileManagementSystem is a **Spring Boot Multi-Module Maven backend application** designed to manage trade file uploads, process trade records, and store trade error information.

The project follows a **modular architecture** that separates backend layers such as **model, DAO, service, controller, and application**, making the system scalable and easy to maintain.

---

## Project Overview

This backend system allows:

- Uploading trade files
- Processing trade records
- Tracking file load details
- Logging trade errors
- Managing trade data in a database

The project is built using **Spring Boot with Maven multi-module architecture**, which improves **code organization and modular development**.

---

## Tech Stack

- Java 21
- Spring Boot
- Spring Data JPA
- Hibernate
- Maven Multi-Module
- MySQL
- Swagger UI
- Postman

---

## Project Architecture

The backend follows a **layered architecture**.

```
Controller Layer
        ↓
Service Layer
        ↓
DAO / Repository Layer
        ↓
Model Layer
        ↓
Database
```

Each layer has a specific responsibility to ensure **clean and maintainable code**.

---

## Project Structure

```
TradeFileManagementSystem
│
├── pom.xml (Parent POM)
│
├── model
│   ├── pom.xml
│   └── src/main/java/com/trade/model
│       ├── entity
│       │   ├── FileLoad.java
│       │   ├── TradeRecord.java
│       │   └── TradeError.java
│       │
│       └── dto
│           └── TradeDTO.java
│
├── dao
│   ├── pom.xml
│   └── src/main/java/com/trade/dao
│       ├── FileLoadRepository.java
│       ├── TradeRecordRepository.java
│       └── TradeErrorRepository.java
│
├── service
│   ├── pom.xml
│   └── src/main/java/com/trade/service
│       ├── FileLoadService.java
│       ├── TradeRecordService.java
│       └── TradeErrorService.java
│
├── controller
│   ├── pom.xml
│   └── src/main/java/com/trade/controller
│       └── TradeController.java
│
└── application
    ├── pom.xml
    └── src/main/java/com/trade
        └── TradeFileManagementApplication.java
```

---

## Module Description

### Parent Module

The **parent module** manages project dependencies and module relationships.

Responsibilities:

- Defines Maven dependency versions
- Controls project build
- Links all modules together

Modules included:

- model
- dao
- service
- controller
- application

---

### Model Module

The **model module** contains data structures used in the system.

Entities include:

- **FileLoad** – stores uploaded file information
- **TradeRecord** – stores trade details
- **TradeError** – stores validation errors

DTOs are used for transferring data between layers.

---

### DAO Module

The **DAO module** contains **Spring Data JPA repositories** responsible for database operations.

Repositories include:

- FileLoadRepository
- TradeRecordRepository
- TradeErrorRepository

Responsibilities:

- Database CRUD operations
- Data persistence
- Query handling

---

### Service Module

The **service module** contains the **business logic** of the system.

Responsibilities:

- Processing trade files
- Validating trade records
- Handling trade errors
- Managing trade data flow between controller and DAO

---

### Controller Module

The **controller module** exposes REST APIs for interacting with the system.

Example APIs:

```
POST /api/trades/upload
GET /api/trades
GET /api/trades/{id}
GET /api/errors
```

Responsibilities:

- Handle HTTP requests
- Send responses to clients
- Connect frontend with backend logic

---

### Application Module

The **application module** contains the main Spring Boot class used to start the application.

```
TradeFileManagementApplication.java
```

Responsibilities:

- Bootstraps the Spring Boot application
- Enables component scanning
- Loads configuration properties

---

## Database Configuration

Example `application.properties` configuration for MySQL.

```
spring.datasource.url=jdbc:mysql://localhost:3306/trade_db
spring.datasource.username=root
spring.datasource.password=yourpassword

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect
```

---

## Running the Application

### 1. Clone the Repository

```
git clone https://github.com/your-username/TradeFileManagementSystem.git
```

### 2. Open Project in IntelliJ

Open the **root project folder** in IntelliJ IDEA.

### 3. Build the Project

```
mvn clean install
```

### 4. Run the Application

Run the main class:

```
TradeFileManagementApplication.java
```

The server will start at:

```
http://localhost:8080
```

---


**Muskan Jha**
