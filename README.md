# Book Inventory Management System

A full-stack web application for managing a book inventory using Node.js, Express, MongoDB, and a simple HTML frontend.

## Features

- **Backend**: RESTful API with Express.js and MongoDB
- **Frontend**: Simple HTML interface with JavaScript for CRUD operations
- **Database**: MongoDB with Mongoose ODM
- **Operations**: Add, view, update, and delete books
- **Inline Editing**: Edit price and stock directly from the table

## Prerequisites

- Node.js (v14 or higher)
- MongoDB (local installation or MongoDB Atlas)

## Installation

1. Clone or download the project files.

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start MongoDB:
   - For local MongoDB: Ensure MongoDB is running on `mongodb://localhost:27017`
   - For MongoDB Atlas: Update the connection string in `server.js`

4. Start the server:
   ```bash
   npm start
   ```

5. Open your browser and navigate to `http://localhost:3000`

## API Endpoints

- `GET /api/books` - Fetch all books
- `POST /api/books` - Add a new book
- `GET /api/books/:id` - Get a specific book by ID
- `PUT /api/books/:id` - Update a book
- `DELETE /api/books/:id` - Delete a book

## Book Schema

```javascript
{
  title: String (required),
  isbn: String (required, unique),
  author: String,
  genre: String,
  price: Number (0-9999),
  stock: Number (default: 0),
  publishedYear: Number,
  createdAt: Date (default: now)
}
```

## Usage

1. **Add a Book**: Fill out the form at the top of the page and click "Add Book"
2. **View Books**: All books are displayed in a table below the form
3. **Edit Price/Stock**: Click the "Edit Price" or "Edit Stock" button next to any book
4. **Delete a Book**: Click the "Delete" button and confirm the deletion

## Development

For development with auto-restart:
```bash
npm run dev
```

This uses `nodemon` to automatically restart the server when files change.

## Notes

- MongoDB connection is set to local by default. Change the connection string in `server.js` for Atlas.
- The frontend uses vanilla JavaScript with fetch API for AJAX requests.
- Error handling is implemented for both frontend and backend.
- ISBN uniqueness is enforced in the database.