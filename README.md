# Blogsyde – Blog Application

A MERN-based blog platform with JWT authentication, protected routes, and a modern React + Tailwind UI. Users can create, manage, and interact with posts and comments, with APIs secured using JWT.

---

## ✨ Features
- User authentication with **JWT** (register, login, logout, profile update)  
- Create, update, publish/unpublish, and delete blog posts  
- Like/dislike posts and manage comments (add, edit, delete, like)  
- Protected routes with role-based access middleware  
- Modern UI with **React, Tailwind CSS, Redux Toolkit**  
- Single deploy: Express serves both the backend APIs and built frontend  

---

## 🧱 Tech Stack
**Frontend:** React, Vite, Tailwind CSS, Redux Toolkit, React Router  
**Backend:** Node.js, Express, MongoDB, Mongoose, JWT, Multer  
**Dev/Build:** Vite, ESLint  

---

## 📁 Project Structure
```
root
├─ backend/
│  ├─ server.js         # Express app, routes, middleware
│  ├─ routes/           # user, blog, comment routes
│  ├─ controllers/      # business logic
│  ├─ middleware/       # JWT auth, multer
│  └─ database/         # MongoDB connection
└─ frontend/
   ├─ src/              # React app source
   └─ dist/             # production build served by Express
```

---

## 🔌 API Overview
Base URL: `/api/v1`

### User
- `POST /user/register` — register  
- `POST /user/login` — login, returns JWT  
- `GET /user/logout` — logout  
- `PUT /user/profile/update` — update profile (protected)  
- `GET /user/all-users` — list all users  

### Blog
- `POST /blog` — create blog (protected)  
- `PUT /blog/:id` — update blog (protected)  
- `PATCH /blog/:id` — publish/unpublish  
- `GET /blog/get-all-blogs` — list all blogs  
- `GET /blog/get-published-blogs` — list published blogs  
- `GET /blog/get-own-blogs` — list my blogs (protected)  
- `DELETE /blog/delete/:id` — delete blog (protected)  
- `GET /blog/:id/like` — like a blog (protected)  
- `GET /blog/:id/dislike` — dislike a blog (protected)  

### Comment
- `POST /comment/:id/create` — add comment to blog (protected)  
- `PUT /comment/:id/edit` — edit comment (protected)  
- `DELETE /comment/:id/delete` — delete comment (protected)  
- `GET /comment/:id/comment/all` — list comments on blog  
- `GET /comment/:id/like` — like comment (protected)  
- `GET /comment/my-blogs/comments` — comments across my blogs (protected)  

---

## ⚙️ Environment Variables
Create a `.env` file in the root:
```
PORT=3000
MONGO_URI=your_mongodb_uri
JWT_SECRET=your_jwt_secret
ORIGIN=http://localhost:5173
```

---

## 🚀 Getting Started

### 1) Clone the repo
```bash
git clone https://github.com/your-username/Blogsyde-Blog-Application.git
cd Blogsyde-Blog-Application
```

### 2) Install dependencies
```bash
# Backend
npm install
# Frontend
npm install --prefix frontend
```

### 3) Run in development
```bash
# Backend with nodemon
npm run dev
# Frontend (Vite)
npm run dev --prefix frontend
```

### 4) Build frontend and serve via Express
```bash
npm run build
npm start
```

---

## 📜 License
MIT (or your choice)
