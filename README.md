# User CRUD API

A RESTful API built using Spring Boot that performs basic CRUD (Create, Read, Update, Delete) operations on a User resource.

## Features

* Create a new user
* Get all users
* Get a user by ID
* Update an existing user
* Delete a user
* UUID-based user IDs
* In-memory data storage using HashMap
* Input validation
* Global exception handling
* Proper HTTP status codes

## Tech Stack

* Java 17
* Spring Boot
* Maven
* Spring Web
* Spring Validation

## User Model

Each user contains the following fields:

```json
{
  "id": "UUID",
  "name": "String",
  "email": "String",
  "age": 20
}
```

## API Endpoints

### Create User

**POST** `/users`

Request Body:

```json
{
  "name": "Deepak",
  "email": "deepak@gmail.com",
  "age": 20
}
```

Response: `201 Created`

---

### Get All Users

**GET** `/users`

Response: `200 OK`

---

### Get User By ID

**GET** `/users/{id}`

Response: `200 OK`

If user does not exist:

```text
404 Not Found
```

---

### Update User

**PUT** `/users/{id}`

Request Body:

```json
{
  "name": "Deepak Pal",
  "email": "deepak123@gmail.com",
  "age": 21
}
```

Response: `200 OK`

---

### Delete User

**DELETE** `/users/{id}`

Response:

```text
204 No Content
```

## Validation Rules

* Name cannot be empty
* Email must be valid
* Age must be greater than 0

Example validation error:

```json
{
  "name": "Name is required",
  "email": "Invalid email format",
  "age": "Age must be positive"
}
```

## Running the Application

Clone the repository:

```bash
git clone <repository-url>
```

Navigate to the project directory:

```bash
cd user-crud-api
```

Run the application:

```bash
mvn spring-boot:run
```

The application will start on:

```text
http://localhost:8080
```

## Project Structure

```text
src/main/java/com/example/demo
│
├── controller
│   └── UserController.java
│
├── service
│   └── UserService.java
│
├── model
│   └── User.java
│
├── exception
│   └── GlobalExceptionHandler.java
│
└── DemoApplication.java
```

## Author

Deepak Pal
