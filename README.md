# Rust CRUD API with PostgreSQL

This is a simple CRUD (Create, Read, Update, Delete) API written in Rust, using the PostgreSQL database for data storage. The API allows you to perform operations on a "User" entity, where each user has an ID, name, and email.

## Getting Started

### Prerequisites

Make sure you have Rust installed on your machine. You can install Rust using [Rustup](https://www.rust-lang.org/tools/install).

You also need a running PostgreSQL database. You can change the database URL in the code to match your PostgreSQL server.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Atarax665/rust-postgres-crud-api.git
   cd rust-postgres-crud-api
   ```

2. Set up the PostgreSQL database:

   Change the `DB_URL` constant in the `main.rs` file to match your PostgreSQL server configuration.

3. Build and run the application:

   ```bash
   cargo build
   cargo run
   ```

The server will start listening on port 8080.

## API Endpoints

### Create a User

```http
POST /api/rust/users
```

Request Body:

```json
{
  "name": "John Doe",
  "email": "john.doe@example.com"
}
```

### Get a User by ID

```http
GET /api/rust/users/{id}
```

### Get All Users

```http
GET /api/rust/users
```

### Update a User by ID

```http
PUT /api/rust/users/{id}
```

Request Body:

```json
{
  "name": "Updated Name",
  "email": "updated.email@example.com"
}
```

### Delete a User by ID

```http
DELETE /api/rust/users/{id}
```

## Response Format

- Success Response:

  ```http
  HTTP/1.1 200 OK
  Content-Type: application/json
  Access-Control-Allow-Origin: *
  Access-Control-Allow-Methods: GET, POST, PUT, DELETE
  Access-Control-Allow-Headers: Content-Type

  {
    "id": 1,
    "name": "John Doe",
    "email": "john.doe@example.com"
  }
  ```

- Error Response (Not Found):

  ```http
  HTTP/1.1 404 NOT FOUND

  User not found
  ```

- Error Response (Internal Error):

  ```http
  HTTP/1.1 500 INTERNAL ERROR

  Internal error
  ```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
