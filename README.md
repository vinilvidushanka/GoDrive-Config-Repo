# ⚙️ GoDrive - Centralized Config Server

## 1. Overview
This repository serves as the **Spring Cloud Config Server** for the **GoDrive** microservice ecosystem. It acts as a centralized source for externalized configuration properties across different environments (e.g., development, production).

## 2. Role in Architecture
* **Centralized Configuration:** Provides a single location to manage properties for all microservices.
* **Environment Management:** Supports environment-specific profiles (default, dev, prod).
* **Dynamic Updates:** Allows microservices to refresh configurations without needing a full restart.

---

## 3. Technology Stack
* **Java 25**
* **Spring Boot**
* **Spring Cloud Config Server**
* **Git** (As the storage backend for configuration files)

---

## 4. Configuration Structure
The repository contains configuration files for the following services:
* `api-gateway.yml`
* `service-registry.yml`
* `vehicle-service.yml`
* `application.yml` (Shared configurations)

---

## 5. How to Access
Once the Config Server is running, configurations can be accessed via:
`http://<config-server-ip>:<port>/<service-name>/<profile>`

Example:
`http://localhost:8888/vehicle-service/default`

---

## 6. Maintenance
To update a configuration:
1. Modify the relevant `.yml` file in this repository.
2. Commit and push the changes to the main branch.
3. Use the `/actuator/refresh` endpoint on the client microservice to apply changes dynamically.
