# Microservices and Spring Concepts Cheat Sheet

This document provides an overview of common questions and answers related to microservices, Spring framework, SQL, Java basics, and related patterns.

---

## Microservices Communication
- **Q**: How do microservices communicate with each other?
- **A**: Microservices communicate through REST APIs, message queues, or event-driven systems. Common tools include API Gateway, which routes requests and handles concerns like security and rate limiting.

---

## API Gateway
- **Q**: What is an API Gateway?
- **A**: An API Gateway serves as a single entry point for client requests, routing them to the appropriate microservices, handling authentication, load balancing, and caching.

---

## Service Discovery in Microservices
- **Q**: How do microservices find each other?
- **A**: Service Discovery enables microservices to locate each other using a registry (like Eureka, Consul). Microservices register their location with the registry, allowing others to query it for their addresses.

---

## Monitoring Microservices
- **Q**: How to monitor microservices?
- **A**: Use tools like Prometheus, Grafana, or ELK Stack to track metrics such as response time, error rate, and throughput. Distributed tracing tools like Zipkin or Jaeger help trace requests across services.

---

## Metering Annotations in Dropwizard
- **Q**: What are `@ExceptionMetered`, `@Metered`, and `@Timed` annotations?
- **A**: 
  - **@ExceptionMetered**: Tracks the rate of exceptions.
  - **@Metered**: Measures the rate at which a method is called.
  - **@Timed**: Records the duration of method executions.

---

## Design Patterns in Microservices
- **Q**: What are some common design patterns in microservices?
- **A**: Key patterns include:
  - **Service Discovery**: For locating services.
  - **Circuit Breaker**: Prevents cascading failures.
  - **Saga**: Manages transactions across services.
  - **API Gateway**: Central access point.

- **Can patterns be combined?** Yes, combining patterns can improve robustness.

---

## Saga Pattern
- **Q**: What is the Saga pattern?
- **A**: A distributed transaction pattern where each service performs its part of a transaction and, in case of failure, compensating actions are performed to maintain data consistency.

---

## Serverless Architecture
- **Q**: What is serverless architecture?
- **A**: Serverless allows running code without managing infrastructure. Functions are executed on-demand, with automatic scaling, billed only for usage (e.g., AWS Lambda, Azure Functions).

---

## Spring’s `@Lookup` Annotation
- **Q**: What is the `@Lookup` annotation?
- **A**: In Spring, `@Lookup` allows injecting a prototype-scoped bean into a singleton-scoped bean. Each time the method annotated with `@Lookup` is called, Spring returns a new instance of the prototype bean.

---

## SQL Joins and Unions
- **Q**: What is the difference between `JOIN` and `UNION`?
- **A**:
  - **JOIN**: Combines columns from tables horizontally based on a related column.
  - **UNION**: Combines result sets vertically, stacking rows from multiple tables.

---

## Stored Procedures
- **Q**: What are stored procedures, and how do you create them?
- **A**: Stored procedures are a group of SQL statements stored together to perform specific operations (e.g., updating multiple tables). They are created using the `CREATE PROCEDURE` statement in SQL.

---

## Bean Lifecycle and Scopes in Spring
- **Q**: What is the Spring bean lifecycle?
- **A**: Spring beans go through phases like initialization, property setting, pre-destroy, and destruction.
- **Q**: What are bean scopes?
- **A**: Common scopes include **singleton** (single instance per Spring container) and **prototype** (new instance on each request).

---

## Prototype Injection into Singleton Beans
- **Q**: How to inject a prototype-scoped bean into a singleton bean?
- **A**: Use the `@Lookup` annotation or a `Provider` to inject a fresh instance of the prototype bean each time it’s needed in a singleton bean.

---

## Java Concepts
- **Q**: Why is the `main` method public and static?
- **A**: `public` allows it to be accessible to the JVM, and `static` enables it to be called without creating an instance of the class.
- **Q**: Can the `main` method be overridden?
- **A**: No, it cannot be overridden since it’s static, but you can overload it with different parameters.

---

## Serialization and Transient Keyword
- **Q**: What is serialization, and why is it in a try-catch block?
- **A**: Serialization converts an object into a byte stream to save or transfer it. It’s wrapped in try-catch to handle potential `IOException`.
- **Q**: What does the `transient` keyword do?
- **A**: The `transient` keyword prevents fields from being serialized.

---

## Memory Leaks in Java
- **Q**: How do memory leaks occur in Java?
- **A**: Memory leaks happen when objects are no longer in use but are still referenced, preventing garbage collection.

---

## Aspect-Oriented Programming (AOP) in Spring
- **Q**: What is AOP in Spring?
- **A**: AOP allows separating cross-cutting concerns (like logging or security) from business logic using aspects, advice, and pointcuts.

---

Save this file as `README.md` in your repository for easy access and documentation. 