# Microservices Architecture - Quarkus, Kafka & Hibernate

## Overview
This diagram represents a **Java microservices architecture** using **Quarkus** for REST APIs, **Kafka** for asynchronous messaging, and **Hibernate** for database persistence.

```mermaid
graph LR
    %% Define node styles
    classDef microservice fill:#ADD8E6,stroke:#000,stroke-width:1px;
    classDef db fill:#D3D3D3,stroke:#000,stroke-width:1px;
    classDef api fill:#90EE90,stroke:#000,stroke-width:1px;
    
    %% Microservices
    Inventory["Inventory Service"]:::microservice
    ItemProducer["Item Producer Service"]:::microservice

    %% Kafka Broker
    Kafka["Kafka Broker"]:::db

    %% Database
    Database["Database (PostgreSQL/MySQL)"]:::db

    %% API Layer
    API["REST API (Quarkus)"]:::api

    %% Software Layers
    Presentation["Presentation Layer"]:::microservice
    Service["Service Layer"]:::microservice
    Data["Data Layer (Hibernate)"]:::db

    %% Relationships
    Inventory -->|new_inventory_state| Kafka
    ItemProducer -->|payment_feed| Kafka
    Kafka --> Inventory
    Kafka --> ItemProducer

    API -->|REST| Inventory
    API -->|REST| ItemProducer

    Inventory --> Service
    ItemProducer --> Service

    Service --> Data
    Data --> Database
```
