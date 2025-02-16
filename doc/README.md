
  # Salary API Documentation:-
  ![image](https://github.com/user-attachments/assets/d99e5344-36da-47dd-bd82-f564858c8858)





| *Author* | *Created on* | *Version* | *Last updated by*|*Internal Reviewer* |*Reviewer L0* |*Reviewer L1* |*Reviewer L2* |
|------------|---------------------------|-------------|---------------------|-------------|-------------|-------------|-------------|
| Mohit Kumar|   10-02-2025             | v1          | Mohit kumar       |  Komal Jaiswal |  |   |      |

___
# Purpose
The purpose of this document is to provide a comprehensive guide on the Salary API, a Java-based microservice responsible for managing all salary-related transactions and records within the **[OT-Microservices](https://github.com/OT-MICROSERVICES/salary-api)** stack 
This platform-independent application can run on multiple operating systems with **[Java Runtime](https://www.java.com/en/download/manual.jsp)** as a requirement.
___
# System Requirements

|   System Requirement              |             Minimum                        |
|-----------------------------------|--------------------------------------------|
| **Processor/Instance Type**           |             Dual Core/t2.medium            | 
| **RAM**                              |               4GB                          |
| **Disk Space**                        |               16GB                         |            
| **OS Required** | Ubuntu 22.04 or 24.04 |


___
# Pre-Requisites
The Salary API application has some database, cache manager and package dependencies. Some of the dependencies are optional and some are mandatory. 
To compile the application, we only need `maven` as a build tool, but for running the application following things are required:-
### **Mandatory Dependencies**
- **[ScyllaDB](https://www.scylladb.com/):** Primary database for storing salary records.
- **[Redis](https://redis.io/):** Cache manager for efficient data retrieval.
- **[Migrate](https://github.com/golang-migrate/migrate):** Database schema migration tool to manage database changes.
- **[Java Runtime Environment (JRE)](https://adoptium.net/):** Required to execute the compiled application.
  
### **Development Dependency**
- **[Maven](https://maven.apache.org/):** Package manager and build tool for compiling and packaging the application.
- **[Java Development Kit (JDK)](https://adoptium.net/):** Required to compile Java source code into bytecode.

___

# Key Components
- **Framework & Language:-**
   Java-based Spring Boot application using embedded Tomcat as a web server.
- **Database & Cache:-**
   ScyllaDB as the primary database.
   Redis as a caching layer.
  
- **Monitoring & Observability:-**
   Prometheus and OpenTelemetry for tracking application metrics.
   Actuator endpoints for health checks and performance insights.
- **API Documentation:-**
   Swagger UI provides interactive documentation for available endpoints and payloads.
- **Migration:-**
    Database schema setup is handled via the Migrate tool using migration.json.
- **Testing & Code Quality:-**
    - JUnit: Unit testing framework.
    - Jacoco: Code coverage reporting.
    - Checkstyle: Code quality enforcement.
___ 

# Important Ports

## Inbound Ports 

|   Port        |    Description     |
| ----------    |    -----------     |
|    **8080**       |   Salary  API port | 
|    **22**         |    SSH            |

## Outbound Port

|   Port        |    Description    |
| ----------    |    -----------    |
|    **9042**      |    Scylla DB      |
|    **6379**      |    Redis          |



___
# Build-Time Dependencies (Required to compile the application)
These dependencies are needed only during the build process to compile the source code and generate a runnable JAR file.

|   **Dependency**      |    **Purpose**   |
| ----------    |    -----------    |
|  **Java 17 (JDK)** |   Required to compile the Java code.     |
|    **Maven**     |    Used as the build tool to resolve dependencies, compile the project, and package it as a JAR file.          |


# Run-Time Dependencies (Required when running the application)

These dependencies must be available when running the built application.

|   **Dependency**      |    **Purpose**  |
| ----------    |    -----------    |
| **Java 17 (JRE)**  |  Required to execute the JAR file.    |
| **ScyllaDB**       |   Primary database for storing salary records. |
| **Redis**     |    Cache manager for fast retrieval of salary data. |
| **Migrate**    |  Used for applying database migrations before running the application.|

___
# Summary

| Dependency   | Build-Time | Run-Time |
|-------------|-----------|----------|
| **Java 17 (JDK)** | ✅ | ✅ (JRE) |
| **Maven** | ✅ | ❌ |
| **ScyllaDB** | ❌ | ✅ |
| **Redis** | ❌ | ✅ |
| **Migrate** | ❌ | ✅ |
___
# Architecture

![image](https://github.com/user-attachments/assets/62b88055-9d8f-4f07-8ac8-ae341bee59ce)

___
# SETUP API  
For a comprehensive, step-by-step guide on setting up the API, follow this link: [Salary Setup](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Nikita-SCRUM-8/OT%20MS%20Understanding/Applications/Salary/POC/README.md)

- After configuring everything, make sure to run the API.
___  
# Runnig the API

``` bash
http://localhost:8080/salary-documentation
```
- **Note:-** Instead of using localhost, use your public IP address so that you can connect to Swagger UI

  ![image](https://github.com/user-attachments/assets/164f9e50-a333-44c1-84d9-49d47e0afd0c)

  ![image](https://github.com/user-attachments/assets/3ea3b791-9c32-4215-be04-f7038cafe97c)

  ![image](https://github.com/user-attachments/assets/ac958552-b659-4c6a-92dc-6ced78931a4d)
___
## Endpoint Information

| **Endpoint**                   | **Method** | **Description**                                                                               |
|--------------------------------|------------|-----------------------------------------------------------------------------------------------|
| **`/api/v1/salary/create/record`** | POST       | Data creation endpoint which accepts certain JSON body to add salary information in database  |
| **`/api/v1/salary/search`**        | GET        | Endpoint for searching data information using the params in the URL                           |
| **`/api/v1/salary/search/all`**    | GET        | Endpoint for searching all information across the system                                      |
| **`/actuator/prometheus`**         | GET        | Application healthcheck and performance metrics are available on this endpoint                |
| **`/actuator/health`**             | GET        | Endpoint for providing shallow healthcheck information about application health and readiness |

___

## Contact Information

| **Name** | **Email address**            |
|----------|-------------------------------|
| Mohit kumar   |  mohit.kumar@mygurukulam.co          |

___
## References

|     Description                  | References  
| ---------------------------------| ------------------------------------------------------------------- |
|     Salary POC      | https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Nikita-SCRUM-8/OT%20MS%20Understanding/Applications/Salary/POC/README.md |
|     Salary Documentation         | |  








  

  

