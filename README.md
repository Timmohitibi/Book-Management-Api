# Book Management API

## Overview
This is a simple Book Management API built using Go and the Gin framework. It provides functionality to:
- Retrieve all books
- Retrieve a book by ID
- Create a new book entry
- Check out a book
- Return a book

## Technologies Used
- Go (Golang)
- Gin Web Framework

## Installation and Setup
### Prerequisites
- Install [Go](https://golang.org/dl/)

### Steps
1. Clone the repository:
   ```sh
   git clone <repository_url>
   cd <repository_directory>
   ```
2. Install dependencies:
   ```sh
   go mod tidy
   ```
3. Run the application:
   ```sh
   go run main.go
   ```

## API Endpoints

### Retrieve all books
- **Endpoint:** `GET /books`
- **Description:** Returns a list of all books.
- **Response:**
  ```json
  [
    { "id": "1", "title": "In Search of Lost Time", "author": "Marcel Proust", "quantity": 2 },
    { "id": "2", "title": "The Great Gatsby", "author": "F. Scott Fitzgerald", "quantity": 5 }
  ]
  ```

### Retrieve book by ID
- **Endpoint:** `GET /books/:id`
- **Description:** Returns details of a book by ID.
- **Response:**
  ```json
  { "id": "1", "title": "In Search of Lost Time", "author": "Marcel Proust", "quantity": 2 }
  ```

### Create a new book
- **Endpoint:** `POST /books`
- **Description:** Adds a new book entry.
- **Request Body:**
  ```json
  { "id": "4", "title": "New Book", "author": "New Author", "quantity": 3 }
  ```
- **Response:**
  ```json
  { "id": "4", "title": "New Book", "author": "New Author", "quantity": 3 }
  ```

### Check out a book
- **Endpoint:** `PATCH /checkout?id=<book_id>`
- **Description:** Decreases book quantity by 1.
- **Response:**
  ```json
  { "id": "1", "title": "In Search of Lost Time", "author": "Marcel Proust", "quantity": 1 }
  ```

### Return a book
- **Endpoint:** `PATCH /return?id=<book_id>`
- **Description:** Increases book quantity by 1.
- **Response:**
  ```json
  { "id": "1", "title": "In Search of Lost Time", "author": "Marcel Proust", "quantity": 3 }
  ```

## Notes
- The application runs on `localhost:8080` by default.
- Ensure you send JSON payloads for `POST` requests.
- Error messages are returned in JSON format.

## License
This project is open-source and available under the [MIT License](LICENSE).

