Create a complete Spring Boot application with the following requirements:

1. Project Structure and Base Setup:
   - Maven-based project with all necessary dependencies
   - Complete pom.xml including Spring Web, Data JPA, Validation, Lombok
   - Proper package structure following domain-driven design
   - Application properties configuration

2. Core Base Operations:
   - Base interface for common CRUD and additional operations
   - Base implementation class
   - Support for pagination, sorting, and filtering
   - Implementation of specification pattern for dynamic queries

3. Domain Layer:
   - Common package with status enums and auditable base class
   - Entity classes with proper JPA annotations
   - Service interfaces extending base operations
   - Service implementations with custom business logic

4. Infrastructure Layer:
   - Custom repository implementations
   - Specification classes for complex queries
   - Persistence configurations
   - Soft delete functionality

5. Web Layer:
   - REST controllers with all CRUD endpoints
   - Custom endpoints for specific operations
   - Request/Response DTOs if applicable
   - Proper error handling

6. Cross-cutting Concerns:
   - Global exception handling
   - Audit logging
   - Entity status management
   - Version control for entities

The result should include everything from basic setup to advanced features like specifications, soft deletes, auditing, and proper error handling, all organized in a clean, maintainable structure.
