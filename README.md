# 🛒 MERN Stack Product Management Application

A full-stack web application built with the MERN stack (MongoDB, Express.js, React, Node.js) for managing products with a modern, responsive user interface.

## 🌐 Live Demo

**Access the application here:** [https://mern-tir5.onrender.com](https://mern-tir5.onrender.com)

> ⚠️ Please wait 1 minute for the server to boot up (Render free tier)

## ✨ Features

- ✅ **Full CRUD Operations** - Create, Read, Update, and Delete products
- 🎨 **Modern UI/UX** - Built with Chakra UI for a beautiful, responsive design
- 🌓 **Dark/Light Mode** - Toggle between color themes
- ⚡ **Real-time Updates** - Instant UI updates without page refreshes
- 📱 **Responsive Design** - Works seamlessly on desktop, tablet, and mobile devices
- 🔔 **Toast Notifications** - User-friendly feedback for all operations
- ✅ **Form Validation** - Client-side validation for required fields
- 🚀 **Production Ready** - Optimized build and deployment configuration

## 🛠️ Tech Stack

### Frontend

- **React 18** - Modern React with functional components and hooks
- **React Router DOM** - Client-side routing
- **Zustand** - Lightweight state management
- **Chakra UI** - Component library for UI design
- **Vite** - Fast build tool and development server
- **React Icons** - Icon library

### Backend

- **Node.js** - JavaScript runtime
- **Express.js** - Web application framework
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **dotenv** - Environment variable management

### Development Tools

- **Nodemon** - Auto-restart server during development
- **ESLint** - Code linting
- **Cross-env** - Cross-platform environment variables

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v14 or higher)
- **npm** or **yarn**
- **MongoDB** (local installation or MongoDB Atlas account)

## 🚀 Installation

1. **Clone the repository**

   ```bash
   git clone <your-repo-url>
   cd MERN
   ```

2. **Install root dependencies**

   ```bash
   npm install
   ```

3. **Install frontend dependencies**

   ```bash
   cd frontend
   npm install
   cd ..
   ```

4. **Set up environment variables**

   Create a `.env` file in the root directory:

   ```env
   MONGO_URI=your_mongodb_connection_string
   PORT=5000
   NODE_ENV=development
   ```

   For MongoDB Atlas:

   - Create a free cluster at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
   - Get your connection string and replace `your_mongodb_connection_string`

   For local MongoDB:

   ```env
   MONGO_URI=mongodb://localhost:27017/mern-products
   ```

## 💻 Running the Application

### Development Mode

1. **Start the backend server**

   ```bash
   npm run dev
   ```

   The server will run on `http://localhost:5000`

2. **Start the frontend development server** (in a new terminal)
   ```bash
   cd frontend
   npm run dev
   ```
   The frontend will run on `http://localhost:5173` (or another port if 5173 is busy)

### Production Mode

1. **Build the frontend**

   ```bash
   npm run build
   ```

2. **Start the production server**
   ```bash
   npm start
   ```

## 📁 Project Structure

```
MERN/
├── backend/
│   ├── config/
│   │   └── db.js              # MongoDB connection configuration
│   ├── controllers/
│   │   └── product.controller.js  # Product CRUD logic
│   ├── models/
│   │   └── product.model.js   # Product Mongoose schema
│   ├── routes/
│   │   └── product.route.js   # Product API routes
│   └── server.js              # Express server setup
├── frontend/
│   ├── public/                # Static assets
│   ├── src/
│   │   ├── components/
│   │   │   ├── Navbar.jsx     # Navigation component
│   │   │   └── ProductCard.jsx # Product card with edit/delete
│   │   ├── pages/
│   │   │   ├── HomePage.jsx   # Product listing page
│   │   │   └── CreatePage.jsx # Create product form
│   │   ├── store/
│   │   │   └── product.js     # Zustand store for state management
│   │   ├── App.jsx            # Main app component
│   │   └── main.jsx           # React entry point
│   ├── index.html
│   ├── vite.config.js         # Vite configuration
│   └── package.json
├── .gitignore
├── package.json               # Root package.json with scripts
└── README.md
```

## 🔌 API Endpoints

### Products API

Base URL: `/api/products`

| Method | Endpoint            | Description          | Request Body             |
| ------ | ------------------- | -------------------- | ------------------------ |
| GET    | `/api/products`     | Get all products     | -                        |
| POST   | `/api/products`     | Create a new product | `{ name, price, image }` |
| PUT    | `/api/products/:id` | Update a product     | `{ name, price, image }` |
| DELETE | `/api/products/:id` | Delete a product     | -                        |

### Request/Response Examples

**Create Product (POST)**

```json
// Request
{
  "name": "Laptop",
  "price": 999.99,
  "image": "https://example.com/laptop.jpg"
}

// Response
{
  "success": true,
  "data": {
    "_id": "...",
    "name": "Laptop",
    "price": 999.99,
    "image": "https://example.com/laptop.jpg",
    "createdAt": "...",
    "updatedAt": "..."
  }
}
```

**Get All Products (GET)**

```json
// Response
{
  "success": true,
  "data": [
    {
      "_id": "...",
      "name": "Laptop",
      "price": 999.99,
      "image": "https://example.com/laptop.jpg",
      "createdAt": "...",
      "updatedAt": "..."
    }
  ]
}
```

## 🗄️ Database Schema

### Product Model

```javascript
{
  name: String (required),
  price: Number (required),
  image: String (required),
  createdAt: Date (auto-generated),
  updatedAt: Date (auto-generated)
}
```

## 🎯 Key Features Explained

### State Management with Zustand

The application uses Zustand for state management, providing a simple and lightweight alternative to Redux. The store handles:

- Product fetching
- Product creation
- Product updates
- Product deletion
- Optimistic UI updates

### Responsive Design

- Mobile-first approach with Chakra UI's responsive breakpoints
- Grid layout that adapts from 1 column (mobile) to 3 columns (desktop)
- Flexible navigation that stacks on smaller screens

### Error Handling

- Server-side validation for required fields
- Client-side error handling with user-friendly toast notifications
- Proper HTTP status codes (200, 201, 400, 404, 500)

## 🚢 Deployment

The application is configured for deployment on platforms like Render, Heroku, or Vercel.

### Environment Variables for Production

```env
MONGO_URI=your_production_mongodb_uri
PORT=5000
NODE_ENV=production
```

### Build Process

1. Frontend is built using Vite, creating optimized production assets
2. Express serves the built frontend files in production mode
3. All routes are handled by React Router (client-side routing)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is open source and available under the [ISC License](LICENSE).

## 👨‍💻 Author

Built with ❤️ using the MERN stack

---

**Note:** Make sure to add your MongoDB connection string to the `.env` file before running the application. Never commit your `.env` file to version control.
