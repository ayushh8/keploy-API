# Book Management App

A full-stack Book Management application with a Node.js + Express + MongoDB backend and a Vite + React frontend. This project includes a complete suite of unit, integration, and API tests.

---

## Tech Stack

### Backend
- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB with Mongoose ODM
- **Testing:** Jest, Supertest

### Frontend
- **Library:** React
- **Build Tool:** Vite
- **Styling:** CSS

---

## Features
- Custom API with at least 4 endpoints: Create, Read (all & by ID), Update, Delete books
- MongoDB database integration for persistent storage
- User-friendly React frontend for interacting with the API
- Environment variables for configuration
- CORS enabled for frontend-backend communication

---

## API Endpoints

All endpoints are prefixed with `/api/books`.

| Method | Endpoint             | Description                |
|--------|----------------------|----------------------------|
| GET    | /api/books           | Get all books              |
| GET    | /api/books/:id       | Get a book by ID           |
| POST   | /api/books           | Add a new book             |
| PUT    | /api/books/:id       | Update a book by ID        |
| DELETE | /api/books/:id       | Delete a book by ID        |

### Sample Requests & Responses

#### Get All Books
- **GET** `/api/books`
- **Response:**
```json
[
  {
    "_id": "...",
    "title": "Book Title",
    "author": "Author Name",
    "genre": "Genre",
    "publishedYear": 2023,
    "createdAt": "...",
    "updatedAt": "..."
  }
]
```

#### Add a Book
- **POST** `/api/books`
- **Body:**
```json
{
  "title": "Book Title",
  "author": "Author Name",
  "genre": "Genre",
  "publishedYear": 2023
}
```
- **Response:**
```json
{
  "_id": "...",
  "title": "Book Title",
  "author": "Author Name",
  "genre": "Genre",
  "publishedYear": 2023,
  "createdAt": "...",
  "updatedAt": "..."
}
```

#### Update a Book
- **PUT** `/api/books/:id`
- **Body:**
```json
{
  "title": "Updated Title",
  "author": "Updated Author",
  "genre": "Updated Genre",
  "publishedYear": 2024
}
```
- **Response:**
```json
{
  "_id": "...",
  "title": "Updated Title",
  "author": "Updated Author",
  "genre": "Updated Genre",
  "publishedYear": 2024,
  "createdAt": "...",
  "updatedAt": "..."
}
```

#### Delete a Book
- **DELETE** `/api/books/:id`
- **Response:**
```json
{
  "message": "Book deleted successfully"
}
```

---

## Database Integration
- **Database Used:** MongoDB
- **Integration:** Mongoose ODM is used to define the Book schema and interact with the MongoDB database. All CRUD operations are performed via Mongoose models.

---

## How to Run the Project

### Backend (API Server)
1.  Navigate to the `backend` directory:
    ```sh
    cd backend
    ```
2.  Install dependencies:
    ```sh
    npm install
    ```
3.  Create a `.env` file with your MongoDB connection string:
    ```env
    PORT=3545
    MONGO_URI=mongodb://127.0.0.1:27017/bookdb
    ```
4.  Ensure MongoDB is running.
5.  Start the server:
    ```sh
    npm run dev
    ```

### Frontend (Web App)
1.  Navigate to the `frontend` directory:
    ```sh
    cd frontend
    ```
2.  Install dependencies:
    ```sh
    npm install
    ```
3.  Start the frontend app:
    ```sh
    npm run dev
    ```
4.  Open the provided URL (e.g., `http://localhost:5173`) in your browser.

---

## Testing

This project uses **Jest** for unit and integration testing and **Supertest** for API endpoint testing.

### How to Run Tests
1.  Navigate to the `backend` directory.
2.  Run all tests:
    ```sh
    npm test
    ```
3.  To generate a coverage report:
    ```sh
    npm run test:coverage
    ```

### Test Coverage
Here is the test coverage report for the API:
![Test Coverage](./API-tested.png)

### Integration Test Results
Screenshot of the successful integration and API tests:
![Integration Test Results](./Integration-tested.png)

### Unit Test Results
Screenshot of the successful unit tests with mocked dependencies:
![Unit Test Results](./unit-tested.png)

---