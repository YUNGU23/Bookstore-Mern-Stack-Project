# Bookstore Mern Stack Project
<p>This comprehensive book store management application is built with the MERN stack (MongoDB, Express.js, React, Node.js). It provides a user-friendly interface for managing a collection of books, including CRUD operations (Create, Read, Update, Delete), detailed book information, and a responsive design.</p>

## Table of Contents
- Features
- Prerequisites
- Installation
- Usage
- Project Structure
- API Endpoints
- Technologies Used
- License
- Author

## Features
### 1. Book Management Operations
- <strong>Add a New Book:</strong> Users can add a new book with details such as title, author, and publish year.
- <strong>View All Books:</strong> Browse a list of all books with basic information.
- <strong>View Detailed Information:</strong> Access detailed information about a specific book, including creation and update timestamps.
- <strong>Edit Book Details:</strong> Modify existing book details, including title, author, and publish year.
- <strong>Delete a Book:</strong> Remove a book from the collection.

### 2. User-Friendly Interface
- <strong>Responsive Design:</strong> The application is designed to be responsive, ensuring a seamless experience on various devices.

## Prerequisites

- Node.js (v14.x or later)
- npm (v7.x or later)
- MongoDB

## Installation
### Backend Setup

1. Initialize a new Node.js project:
```
mkdir backend
cd backend
npm init -y
```

2. Install required packages:
```
npm install express mongoose cors
```

3. Create a server.js file:
```
import express from "express";
import mongoose from "mongoose";
import cors from "cors";

const app = express();

// Middleware for parsing request body
app.use(express.json());

// Middleware for handling CORS Policy
app.use(cors());

// Routes setup (booksRoute.js)

// MongoDB connection setup

const PORT = 5555;

mongoose
  .connect("YOUR_MONGODB_URL", { useNewUrlParser: true, useUnifiedTopology: true })
  .then(() => {
    console.log("App connected to database");
    app.listen(PORT, () => {
      console.log(`App is listening on port: ${PORT}`);
    });
  })
  .catch((err) => {
    console.log(err);
  });
  ```

4. Create a routes/booksRoute.js file:
```
import express from "express";
import { Book } from "../models/bookModel.js";

const router = express.Router();

// CRUD routes go here

export default router;
```

### Frontend Setup
1. Initialize a new React project:
```
npx create-react-app frontend
cd frontend
```

2. Install required packages:
```
npm install axios react-router-dom notistack react-icons tailwindcss
```

3. Create a src/api.js file:
```
import axios from "axios";

const instance = axios.create({
  baseURL: "http://localhost:5555", // Your backend URL
});

export default instance;
```
4. Create a `src/components folder` for React components. 

5. Tailwind CSS Setup:

- Create a `tailwind.css` file in the `src`folder.
    ```
    @import 'tailwindcss/base';
    @import 'tailwindcss/components';
    @import 'tailwindcss/utilities';
    ```
- Update `src/index.css` to include the Tailwind styles.
    ```
    @import './tailwind.css';
    ```
### Run the Application
1. Run the backend:
```
npm start
```

2. Run the frontend:
In another terminal window:
```
npm start
```

## Usage
1. Start the Backend Server:
```
cd backend
npm start
```
The server will be running at http://localhost:5555.


2. Start the Frontend Development Server:
```
cd frontend
npm run dev
```
Open your browser and visit http://localhost:3000 to use the application.

## Project Structure
- <strong>backend:</strong> Contains the Express.js server code and MongoDB database models.
- <strong>frontend:</strong> Contains the React.js frontend code.

## API Endpoints
- <strong>POST /books:</strong> Create a new book.
- <strong>GET /books:</strong> Get all books.
- <strong>GET /books/:id:</strong> Get details of a specific book by ID.
- <strong>PUT /books/:id:</strong> Update details of a specific book by ID.
- <strong>DELETE /books/:id:</strong> Delete a book by ID.

## Technologies Used
- <strong>Node.js:</strong> Used to run the backend server and manage server-side logic.
- <strong>Express.js:</strong> Employed to create RESTful API endpoints for handling CRUD operations related to books.
- <strong>Vite + React:</strong> Used for frontend development, offering features like hot module replacement (HMR) and optimized build performance.
- <strong>MongoDB:</strong> Used to store and retrieve book data efficiently, ensuring scalability and flexibility.
- <strong>Mongoose:</strong> Employed to define the data schema for books and interact with the MongoDB database.
- <strong>Axios:</strong> Used to make HTTP requests from the frontend to the backend API, facilitating data retrieval and manipulation.
- <strong>React Router:</strong> Manages navigation within the React app, enabling users to switch between different views.
- <strong>Notistack:</strong> Employed to display user-friendly notifications based on the outcomes of CRUD operations or other user actions.
- <strong>Tailwind CSS:</strong> Used for styling frontend components and layout, ensuring a clean and responsive user interface.

## License
This project is licensed under the ISC License.

## Author
- Yun Gu
    - GitHub: https://github.com/yungu23
    - LinkedIn: https://linkedin.com/in/yun-gu
