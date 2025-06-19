# Book Management App

A full-stack Book Management application with a Node.js + Express + MongoDB backend and a Vite + React frontend.

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
1. Go to the backend directory:
   ```sh
   cd backend
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Create a `.env` file:
   ```env
   PORT=3545
   MONGO_URI=mongodb://127.0.0.1:27017/bookdb
   ```
4. Start MongoDB (locally or use MongoDB Atlas).
5. Start the backend server:
   ```sh
   npm run dev
   # or
   node server.js
   ```

### Frontend (Web App)
1. Go to the frontend directory:
   ```sh
   cd frontend
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Start the frontend:
   ```sh
   npm run dev
   ```
4. Open the provided local URL (e.g., http://localhost:5173) in your browser.

---

## How to Interact with the API
- Use the frontend web app to create, read, update, and delete books.
- Alternatively, use Postman or curl to test the API endpoints directly.

### Example curl Commands

**Add a Book:**
```sh
curl -X POST http://localhost:3545/api/books -H "Content-Type: application/json" -d '{"title":"The Hobbit","author":"J.R.R. Tolkien","genre":"Fantasy","publishedYear":1937}'
```

**Get All Books:**
```sh
curl http://localhost:3545/api/books
```

**Update a Book:**
```sh
curl -X PUT http://localhost:3545/api/books/<BOOK_ID> -H "Content-Type: application/json" -d '{"title":"Updated Title","author":"Updated Author","genre":"Updated Genre","publishedYear":2024}'
```

**Delete a Book:**
```sh
curl -X DELETE http://localhost:3545/api/books/<BOOK_ID>
```

---

## Project Structure

```
keploy-API/
  backend/
    models/
    routes/
    controllers/
    config/
    server.js
    package.json
    .env
  frontend/
    src/
    public/
    package.json
    ...
  README.md
```

---