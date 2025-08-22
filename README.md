# 🎙️ PODCASTER – MERN Stack Application

A full-stack **MERN (MongoDB, Express.js, React, Node.js)** application for podcast hosting, listening, and management.  
The system is built with modular architecture, supporting **authentication, CRUD operations for podcasts, file uploads, and secure APIs**.

---

## 📌 System Architecture

- **Frontend (React + Vite)**
  - Component-driven UI (functional components with hooks)
  - React Router for navigation
  - State management with Context/Redux
  - TailwindCSS for styling
  - Axios for REST API integration

- **Backend (Node + Express + MongoDB)**
  - RESTful API design
  - JWT-based authentication & authorization
  - Multer for file uploads (images/audio)
  - MongoDB (Mongoose ODM) for persistence
  - Layered structure: `routes → controllers → services → models`

---

## 📂 Project Structure

```
PODCASTER/
│
├── backend/                # Express.js + MongoDB backend
│   ├── routes/             # API endpoints (user, podcast, categories)
│   ├── models/             # MongoDB schemas (User, Podcast, Category)
│   ├── uploads/            # Uploaded audio/images (ignored in .gitignore)
│   ├── package.json
│   └── server.js
│
├── frontend/               # React + Vite frontend
│   ├── src/
│   │   ├── components/     # Reusable components (Navbar, Player, etc.)
│   │   ├── pages/          # Views (Login, Signup, Home, Profile, etc.)
│   │   ├── store/          # State management
│   │   ├── App.jsx         # Root component
│   │   └── main.jsx        # Entry point
│   ├── public/
│   ├── package.json
│   └── vite.config.js
│
└── README.md
```

---

## ⚙️ Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/<username>/PODCASTER.git
cd PODCASTER
```

### 2. Backend Setup
```bash
cd backend
npm install
```

Create `.env` inside `backend/`:
```env
PORT=5000
MONGO_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/podcaster
JWT_SECRET=<your_secret_key>
```

Run the backend:
```bash
npm start
```

### 3. Frontend Setup
```bash
cd frontend
npm install
npm run dev
```

Frontend runs on `http://localhost:5173` (Vite default)  
Backend runs on `http://localhost:5000`

---

## 🔑 API Endpoints

### Auth
- `POST /api/auth/register` – Create account
- `POST /api/auth/login` – Login & JWT token
- `GET /api/auth/profile` – Get user profile (protected)

### Podcasts
- `POST /api/podcasts/` – Upload new podcast (with audio/image)
- `GET /api/podcasts/` – Fetch all podcasts
- `GET /api/podcasts/:id` – Fetch single podcast
- `PUT /api/podcasts/:id` – Update podcast (owner only)
- `DELETE /api/podcasts/:id` – Delete podcast (owner only)

### Categories
- `GET /api/categories/` – Fetch all categories
- `POST /api/categories/` – Create new category

---

## 🛠️ Key Dependencies

### Backend
- `express` – Web framework
- `mongoose` – MongoDB ODM
- `jsonwebtoken` – Authentication
- `multer` – File uploads
- `bcrypt` – Password hashing
- `cors` – Cross-origin requests

### Frontend
- `react` – UI library
- `react-router-dom` – Routing
- `axios` – API requests
- `tailwindcss` – Styling
- `vite` – Development/build tool

---

## ⚡ Development Notes

- **Uploads**: Stored in `/backend/uploads/` (ignored in Git, consider moving to cloud storage in production).
- **Auth flow**: JWT is stored in localStorage; attach token in `Authorization` header for protected routes.
- **Error handling**: Centralized error middleware in Express.
- **Frontend routing**: Protected routes redirect to `/login` if user is unauthenticated.

---

## 🔮 Future Enhancements

- Replace local file storage with **AWS S3 / Cloudinary**
- Add **podcast analytics** (views, listens, downloads)
- Real-time **chat/feedback system**
- AI-based **recommendation engine**
- Support for **subscriptions & monetization**

---

## 👨‍💻 Contributors

- **A. Vishnuvardhan Reddy (21MIC7020)**
- **A. Ruthvik Reddy (21MIC7101)**
- **M. V. P. Kashyap (21MIC7085)**

---

## 📜 License

This project is licensed under the **MIT License**.
