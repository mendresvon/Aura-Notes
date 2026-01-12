# 🌟 Aura Notes

<div align="center">

![Status](https://img.shields.io/badge/status-active-success.svg)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?logo=mongodb&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-000000?logo=express&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-339933?logo=node.js&logoColor=white)

**A full-stack note-taking application inspired by Google Keep, featuring dynamic note sizing and a responsive masonry layout**

</div>

---

## 📋 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Getting Started](#-getting-started)
- [API Documentation](#-api-documentation)
- [Screenshots](#-screenshots)
- [Performance & Security](#-performance--security)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [Contact](#-contact)

---

## 🎯 About

**Aura Notes** is a full-stack note-taking application inspired by **Google Keep**, built with the MERN stack (MongoDB, Express.js, React, Node.js). It features **dynamic note sizing** where note height adapts to content length, creating a responsive masonry layout that provides an intuitive, visually appealing user experience.

The application combines powerful backend architecture with a visually stunning frontend featuring animated UI components, glassmorphism effects, and smooth Framer Motion transitions. The adaptive card layout demonstrates **CSS Grid mastery** and attention to UX detail.

This project demonstrates proficiency in:
- Full-stack JavaScript development
- RESTful API design and implementation
- JWT-based authentication & authorization
- Modern React patterns (Context API, hooks, protected routes)
- Responsive UI/UX design with TailwindCSS
- Database modeling with MongoDB & Mongoose
- Production deployment (Vercel frontend, cloud backend)

---

## ✨ Features

### 🔐 **Authentication & Security**
- Secure user registration and login with **JWT** tokens
- Password hashing using **bcryptjs**
- Protected routes with authentication middleware
- Token-based session management
- Email validation and password strength enforcement

### 📝 **Note Management**
- **Create, Read, Update, Delete (CRUD)** operations for notes
- **Dynamic note sizing** - height adapts to content length
- **Masonry layout** inspired by Google Keep
- Real-time note filtering and search functionality
- Notes sorted by most recently updated
- User ownership validation for all operations
- Modal-based editing interface

### 🎨 **Modern UI/UX**
- **Google Keep-inspired** design with adaptive card layout
- **Responsive masonry grid** using CSS Grid
- Stunning **glassmorphic** design with backdrop blur effects
- Animated **gradient backgrounds** with floating blobs
- Custom **glowing cursor** effect
- Smooth **Framer Motion** animations
- Fully **responsive** design (mobile, tablet, desktop)
- Dark theme optimized for reduced eye strain

### 🚀 **Performance**
- **Vite** for lightning-fast builds and HMR (Hot Module Replacement)
- Optimized bundle size with code splitting
- Efficient state management with React Context
- CORS-protected API endpoints

---

## 🛠️ Tech Stack

### **Frontend**
| Technology | Purpose |
|------------|---------|
| **React 19** | Modern UI library with latest features |
| **Vite** | Next-generation build tool for fast development |
| **TailwindCSS 4** | Utility-first CSS framework |
| **Framer Motion** | Production-ready animation library |
| **React Router v7** | Client-side routing |
| **Axios** | Promise-based HTTP client |
| **React Modal** | Accessible modal dialog component |
| **date-fns** | Modern date utility library |

### **Backend**
| Technology | Purpose |
|------------|---------|
| **Node.js** | JavaScript runtime |
| **Express.js** | Minimal web framework |
| **MongoDB** | NoSQL database |
| **Mongoose** | MongoDB object modeling |
| **JWT** | Secure authentication tokens |
| **bcryptjs** | Password hashing |
| **dotenv** | Environment variable management |
| **CORS** | Cross-origin resource sharing |

### **Development Tools**
- **ESLint** - Code linting and quality
- **Vitest** - Unit testing framework
- **Nodemon** - Auto-restart during development
- **Git** - Version control

---

## 🏗️ Architecture

```
aura-notes/
├── aura-notes-frontend/          # React frontend application
│   ├── src/
│   │   ├── components/           # Reusable React components
│   │   │   ├── NoteCard.jsx     # Individual note display
│   │   │   ├── NoteForm.jsx     # Create/edit note form
│   │   │   ├── GlowingCursor.jsx # Custom cursor effect
│   │   │   └── ProtectedRoute.jsx # Auth guard component
│   │   ├── context/
│   │   │   └── AuthContext.jsx  # Authentication state management
│   │   ├── pages/
│   │   │   ├── LoginPage.jsx    # User login
│   │   │   ├── RegisterPage.jsx # User registration
│   │   │   └── DashboardPage.jsx # Main notes dashboard
│   │   ├── services/
│   │   │   └── api.js           # API client & endpoints
│   │   ├── App.jsx              # Main app component
│   │   └── index.css            # Global styles & animations
│   └── package.json
│
└── aura-notes-backend/           # Express.js backend API
    ├── models/
    │   ├── User.js              # User schema & model
    │   └── Note.js              # Note schema & model
    ├── routes/
    │   ├── auth.js              # Authentication endpoints
    │   └── notes.js             # Note CRUD endpoints
    ├── middleware/
    │   └── auth.js              # JWT verification middleware
    ├── index.js                 # Server entry point
    └── package.json
```

### **Data Flow**
1. User authenticates via `/api/auth/login` or `/api/auth/register`
2. Server returns JWT token stored in localStorage
3. Protected routes include token in Authorization header
4. Middleware validates token and attaches user to request
5. Controllers perform CRUD operations with ownership validation
6. MongoDB stores and retrieves data via Mongoose models

---

## 🚀 Getting Started

### **Prerequisites**
- **Node.js** (v16 or higher)
- **npm** or **yarn**
- **MongoDB** (local installation or MongoDB Atlas account)
- **Git**

### **Installation**

1. **Clone the repository**
```bash
git clone https://github.com/breznev/aura-notes.git
cd aura-notes
```

2. **Backend Setup**
```bash
cd aura-notes-backend
npm install
```

3. **Configure environment variables**
Create a `.env` file in `aura-notes-backend/`:
```env
MONGO_URI=mongodb://localhost:27017/aura-notes
# Or use MongoDB Atlas:
# MONGO_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/aura-notes

JWT_SECRET=your_super_secret_jwt_key_here_change_this
PORT=3001
```

4. **Start the backend server**
```bash
npm run dev  # Development mode with nodemon
# or
npm start    # Production mode
```

Server runs on `http://localhost:3001`

5. **Frontend Setup** (in a new terminal)
```bash
cd aura-notes-frontend
npm install
```

6. **Configure frontend API endpoint** (if needed)
Update `src/services/api.js` if your backend runs on a different port:
```javascript
const API_URL = 'http://localhost:3001/api';
```

7. **Start the frontend development server**
```bash
npm run dev
```

Frontend runs on `http://localhost:5173`

### **Build for Production**

**Frontend:**
```bash
cd aura-notes-frontend
npm run build
npm run preview  # Test production build locally
```

**Backend:**
```bash
cd aura-notes-backend
npm start
```

---

## 📡 API Documentation

### **Authentication Endpoints**

#### **POST** `/api/auth/register`
Register a new user
```json
// Request
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "securePassword123"
}

// Response (201 Created)
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": "60d5ec49f1b2c72b8c8e4f1a",
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```

#### **POST** `/api/auth/login`
Login existing user
```json
// Request
{
  "email": "john@example.com",
  "password": "securePassword123"
}

// Response (200 OK)
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": "60d5ec49f1b2c72b8c8e4f1a",
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```

#### **GET** `/api/auth/me`
Get current user (requires authentication)
```json
// Headers
Authorization: Bearer <token>

// Response (200 OK)
{
  "id": "60d5ec49f1b2c72b8c8e4f1a",
  "name": "John Doe",
  "email": "john@example.com"
}
```

---

### **Note Endpoints** (All require authentication)

#### **POST** `/api/notes`
Create a new note
```json
// Headers
Authorization: Bearer <token>

// Request
{
  "title": "Meeting Notes",
  "content": "Discussed project timeline and deliverables..."
}

// Response (201 Created)
{
  "_id": "60d5ec49f1b2c72b8c8e4f1b",
  "user": "60d5ec49f1b2c72b8c8e4f1a",
  "title": "Meeting Notes",
  "content": "Discussed project timeline and deliverables...",
  "createdAt": "2024-01-13T03:52:48.000Z",
  "updatedAt": "2024-01-13T03:52:48.000Z"
}
```

#### **GET** `/api/notes`
Get all notes for authenticated user
```json
// Headers
Authorization: Bearer <token>

// Response (200 OK)
[
  {
    "_id": "60d5ec49f1b2c72b8c8e4f1b",
    "user": "60d5ec49f1b2c72b8c8e4f1a",
    "title": "Meeting Notes",
    "content": "Discussed project timeline...",
    "createdAt": "2024-01-13T03:52:48.000Z",
    "updatedAt": "2024-01-13T03:52:48.000Z"
  }
]
```

#### **PUT** `/api/notes/:id`
Update an existing note
```json
// Headers
Authorization: Bearer <token>

// Request
{
  "title": "Updated Meeting Notes",
  "content": "Updated content..."
}

// Response (200 OK)
{
  "_id": "60d5ec49f1b2c72b8c8e4f1b",
  "title": "Updated Meeting Notes",
  "content": "Updated content...",
  // ... other fields
}
```

#### **DELETE** `/api/notes/:id`
Delete a note
```json
// Headers
Authorization: Bearer <token>

// Response (200 OK)
{
  "msg": "Note removed"
}
```

---

## 📸 Screenshots

> **Note:** Add screenshots of your application here to showcase the UI

**Dashboard View**
- Masonry layout with animated notes
- Glowing cursor effect
- Search functionality

**Authentication Pages**
- Modern login/register forms
- Animated gradient backgrounds
- Form validation

**Note Modal**
- Glassmorphic design
- Smooth animations
- Intuitive editing interface

---

## 🔒 Performance & Security

### **Security Implementations**
- ✅ **Password Hashing** - bcryptjs with salt rounds
- ✅ **JWT Authentication** - Secure token-based auth
- ✅ **Input Validation** - Email format and password length validation
- ✅ **Authorization** - User-specific note access control
- ✅ **CORS Protection** - Whitelist-based origin validation
- ✅ **Environment Variables** - Sensitive data in `.env` files

### **Performance Optimizations**
- ✅ **Vite Build Tool** - Fast builds and HMR
- ✅ **Code Splitting** - Optimized bundle sizes
- ✅ **Lazy Loading** - Components loaded on demand
- ✅ **Database Indexing** - Mongoose schema indexes
- ✅ **Debounced Search** - Efficient real-time filtering

---

## 🗺️ Roadmap

### **Planned Features**
- [ ] Rich text editor with markdown support
- [ ] Note categories and tags
- [ ] Color-coded notes
- [ ] Collaborative notes (share with other users)
- [ ] File attachments (images, PDFs)
- [ ] Dark/light theme toggle
- [ ] Export notes (PDF, Markdown)
- [ ] Mobile app (React Native)
- [ ] Real-time sync with WebSockets
- [ ] Trash/archive functionality

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

---

## 📫 Contact

**Your Name** - [@yourtwitter](https://twitter.com/yourtwitter) - your.email@example.com

Project Link: [https://github.com/breznev/aura-notes](https://github.com/breznev/aura-notes)

Live Demo: [https://aura-notes-xi.vercel.app](https://aura-notes-xi.vercel.app)

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- [React Documentation](https://react.dev/)
- [TailwindCSS](https://tailwindcss.com/)
- [Framer Motion](https://www.framer.com/motion/)
- [MongoDB University](https://university.mongodb.com/)
- [Vercel](https://vercel.com/) for hosting

---

<div align="center">

**Built with ❤️ using the MERN Stack**

⭐ Star this repo if you found it helpful!

</div>
