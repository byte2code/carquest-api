# CarQuest API

Spring Boot REST API for managing cars with MySQL persistence, JWT authentication, Argon2 password encoding, and review-service integration via `RestTemplate`.

## Overview

CarQuest is a compact Spring Boot project that demonstrates a secured CRUD-style REST API for car records. It includes user registration and JWT-based login, then protects car operations behind stateless bearer-token authentication.

This version integrates with an external Review Service: `GET /car/{name}` enriches the response with review strings fetched over HTTP, and `POST /car/addCarReview` forwards a review request to the review service.

## Concepts and Features Covered

- Spring Boot REST API setup
- Spring Data JPA repository pattern
- MySQL-backed persistence
- Spring Security with JWT authentication (stateless)
- Argon2 password encoding for registered users
- Public user registration and token-based login flow
- CRUD-style endpoints for car records
- Inter-service communication with a review service using `RestTemplate`

## Tech Stack

- Java 17
- Spring Boot 2.7
- Spring Web
- Spring Data JPA
- Spring Security
- Spring Validation
- MySQL
- Maven
- Lombok
- JJWT

## Project Structure

```text
CarQuest/
├── CHANGELOG.md
├── README.md
├── pom.xml
├── mvnw
├── mvnw.cmd
├── review-service/
└── src/
    ├── main/
    │   ├── java/com/CN/CarQuest/
    │   │   ├── communicator/
    │   │   ├── config/
    │   │   ├── controller/
    │   │   ├── dto/
    │   │   ├── exceptions/
    │   │   ├── jwt/
    │   │   ├── model/
    │   │   ├── repository/
    │   │   ├── security/
    │   │   ├── service/
    │   │   └── CarQuestApplication.java
    │   └── resources/
    │       └── application.yml
    └── test/
        └── java/
```

## How to Run

1. Open a terminal in the project root.
2. Update MySQL connection values in `src/main/resources/application.yml` if needed.
3. Run `./mvnw test` (fallback: `mvn test`).
4. Run `./mvnw spring-boot:run`.
5. Register a user with `POST /user/register`.
6. Obtain a token with `POST /auth/login`.
7. Call protected endpoints with `Authorization: Bearer <token>`.

Available endpoints:

- `POST /auth/login`
- `GET /user`
- `POST /user/register`
- `GET /car/getAll`
- `GET /car/{name}`
- `POST /car/add`
- `POST /car/addCarReview`
- `PUT /car/{name}`
- `DELETE /car/{name}`

## Review Service Dependency

This version expects a separate Review Service to be running. The default URLs in `ReviewServiceCommunicator` point to:

- `POST http://localhost:8082/review/add`
- `GET http://localhost:8082/review/car/{carName}`

If you’re using the bundled `review-service/` folder from v2, note its routes/port may differ; keep code unchanged and align your local services accordingly when running.

## GitHub Metadata

- Suggested repository description: `Spring Boot REST API for car management with MySQL persistence, JWT authentication, Argon2 password encoding, and review-service integration via RestTemplate.`
- Suggested topics: `java`, `java-17`, `spring-boot`, `spring-security`, `spring-data-jpa`, `mysql`, `rest-api`, `jwt`, `argon2`, `resttemplate`, `microservices`, `car-management`, `maven`, `learning-project`, `portfolio-project`

