# CarQuest API

Spring Boot REST API for managing cars with MySQL persistence, JWT authentication, and Argon2 password encoding.

## Overview

CarQuest is a compact Spring Boot project that demonstrates a secured CRUD-style REST API for car records. It includes user registration and JWT-based login, then protects car operations behind stateless bearer-token authentication.

## Concepts and Features Covered

- Spring Boot REST API setup
- Spring Data JPA repository pattern
- MySQL-backed persistence
- Spring Security with JWT authentication (stateless)
- Argon2 password encoding for registered users
- Public user registration and token-based login flow
- CRUD-style endpoints for car records

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
└── src/
    ├── main/
    │   ├── java/com/CN/CarQuest/
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

Example request body for user registration:

```json
{
  "username": "john",
  "password": "john123"
}
```

Example request body for login:

```json
{
  "username": "john",
  "password": "john123"
}
```

Example request body for adding a car:

```json
{
  "name": "i20",
  "brand": "Hyundai",
  "color": "White",
  "modelYear": 2022,
  "price": 850000
}
```

## Learning Highlights

- Demonstrates JWT-secured REST endpoints using a custom `OncePerRequestFilter`
- Shows Argon2 password hashing configuration for user registration
- Uses JPA repositories to keep persistence simple for CRUD flows

## GitHub Metadata

- Suggested repository description: `Spring Boot REST API for car management with MySQL persistence, JWT authentication, and Argon2 password encoding.`
- Suggested topics: `java`, `java-17`, `spring-boot`, `spring-security`, `spring-data-jpa`, `mysql`, `rest-api`, `jwt`, `argon2`, `car-management`, `maven`, `learning-project`, `portfolio-project`

