# Microservices Architecture - Quarkus, Kafka & Hibernate

## Overview
This project is a **Java backend architecture** built using **microservices**. It leverages **Quarkus** for REST APIs, **Kafka** for asynchronous messaging, and **Hibernate** for database persistence.

## Technologies Used
- **Quarkus**: Lightweight Java framework optimized for microservices and cloud.
- **Kafka**: Message broker for event-driven communication.
- **Hibernate ORM**: Object-relational mapping for database interaction.
- **REST API**: Exposes endpoints for client-server communication.
- **DTO (Data Transfer Object)**: Standardized data exchange format.

## Architecture Overview
This system follows a modular architecture consisting of multiple **microservices** that communicate through **Kafka** and expose a REST API via Quarkus.

### **1. Microservices**
- **Inventory Service**: Manages stock levels and publishes updates via Kafka.
- **Item Producer Service**: Produces items and sends events to Kafka.
- **Additional Services**: Can be extended as needed.

### **2. Communication & Integration**
- **Kafka** is used to handle events like `new_inventory_state` and `payment_feed`.
- **REST API** endpoints are exposed via **Quarkus** to enable external interactions.

### **3. Software Layers**
- **Presentation Layer**: Handles REST API requests.
- **Service Layer**: Implements business logic.
- **Data Layer**: Uses Hibernate ORM for database persistence.

### **4. External Components**
- **Database (PostgreSQL/MySQL)**: Stores inventory and item data.
- **Client Applications**: Interact with the backend via REST API.

## Installation & Setup

### **Prerequisites**
- **Java 17+**
- **Maven**
- **Docker (for Kafka)**
- **PostgreSQL/MySQL (for data persistence)**
