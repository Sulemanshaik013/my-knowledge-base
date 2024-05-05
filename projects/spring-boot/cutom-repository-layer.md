# **Custom Repository Layer Using Spring JdbcTemplate (No JPA)**

## **1. Purpose**

Build a **JPA-free repository layer** for Spring Boot applications that interact with a **relational database**.
The repository must use **JdbcTemplate**, support CRUD operations, soft deletion, pagination, and clean separation of domain and infrastructure layers.

---

## **2. Scope**

This project delivers a reusable repository pattern including:

* Domain entity (example: `Customer`)
* Repository interfaces (domain layer)
* Spring-based JdbcTemplate repository implementation (infrastructure layer)
* RowMapper for entity mapping
* Externalized SQL
* Logging, error handling, soft delete, and resilience

---

## **3. Functional Requirements**

### **3.1 Repository Operations**

Create an interface with:

* `findById(id)`
* `findAll(page, pageSize)`
* `save(entity)`
* `update(entity)`
* `deleteById(id)` → soft delete (set `deleted_at`)
* Optional: `findByFilters(...)` extension-friendly

### **3.2 Data Access Implementation**

Repository implementation must:

* Use **JdbcTemplate**
* Use **prepared statements only**
* Map rows via `RowMapper<T>`
* Implement pagination using SQL `LIMIT/OFFSET`
* Exclude soft-deleted rows in queries
* Use SQL loaded from:

  * `/resources/sql/*.sql`
    or
  * property keys

### **3.3 Error Handling**

* Wrap failures in custom exceptions (e.g., `CustomerRepositoryException`)
* Log:

  * Inputs
  * SQL execution
  * Failures + stack traces

### **3.4 Resilience**

* Handle transient DB errors
* Implement retry logic (if enabled)
* Use connection pooling (HikariCP)

---