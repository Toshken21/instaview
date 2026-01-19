# 🌿 Serenity - MERN Authentication App

A full-stack authentication application built with MongoDB, Express, React, and Node.js featuring a calming, nature-inspired design.

![Node.js](https://img.shields.io/badge/Node.js-18+-green)
![MongoDB](https://img.shields.io/badge/MongoDB-6+-green)
![React](https://img.shields.io/badge/React-18-blue)

## ✨ Features

- **User Registration** - Create new accounts with username/password
- **User Login** - Secure authentication with JWT tokens
- **User Dashboard** - View logged-in user profile
- **Account Deletion** - Remove user accounts
- **Password Hashing** - Secure bcrypt password storage
- **JWT Authentication** - Stateless token-based auth
- **Calming UI** - Sage green, soft blue color palette

## 📁 Project Structure

```
mern-auth-app/
├── server/                 # Express backend
│   ├── models/
│   │   └── User.js        # Mongoose User schema
│   ├── routes/
│   │   └── auth.js        # Authentication routes
│   ├── server.js          # Express server entry
│   ├── package.json
│   └── .env.example       # Environment template
│
└── client/                 # React frontend
    ├── public/
    │   └── index.html
    ├── src/
    │   ├── App.js         # Main React component
    │   └── index.js       # React entry point
    └── package.json
```

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ installed
- MongoDB running locally or MongoDB Atlas account
- npm or yarn

### 1. Clone and Setup Server

```bash
cd server

# Install dependencies
npm install

# Create environment file
cp .env.example .env

# Edit .env with your settings:
# - MONGODB_URI: Your MongoDB connection string
# - JWT_SECRET: A strong random secret key
```

### 2. Configure Environment Variables

Edit `server/.env`:

```env
# For local MongoDB
MONGODB_URI=mongodb://localhost:27017/mern-auth

# For MongoDB Atlas
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/mern-auth

# Generate a strong secret (use a random string generator)
JWT_SECRET=your-super-secret-key-at-least-32-chars

PORT=5000
```

### 3. Start the Server

```bash
cd server
npm run dev    # Development with nodemon
# or
npm start      # Production
```

Server runs at `http://localhost:5000`

### 4. Setup and Start Client

```bash
cd client

# Install dependencies
npm install

# Start development server
npm start
```

Client runs at `http://localhost:3000`

## 🔌 API Endpoints

### Authentication Routes

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/api/auth/register` | Register new user | No |
| POST | `/api/auth/login` | Login user | No |
| GET | `/api/auth/me` | Get current user | Yes |
| PUT | `/api/auth/update` | Update user | Yes |
| DELETE | `/api/auth/delete` | Delete user | Yes |

### Request/Response Examples

**Register:**
```bash
curl -X POST http://localhost:5000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{"username": "john", "password": "secret123"}'
```

**Login:**
```bash
curl -X POST http://localhost:5000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"username": "john", "password": "secret123"}'
```

**Get Current User:**
```bash
curl http://localhost:5000/api/auth/me \
  -H "Authorization: Bearer YOUR_JWT_TOKEN"
```

## 🎨 Design System

The app uses a calming, nature-inspired color palette:

| Color | Hex | Usage |
|-------|-----|-------|
| Sage Green | `#7c9885` | Primary actions, accents |
| Soft Teal | `#93b4ba` | Secondary elements |
| Deep Forest | `#3d4f4f` | Primary text |
| Mist | `#6b8080` | Secondary text |
| Cloud | `#e8f0e9` | Background gradient start |
| Seafoam | `#c5dde0` | Background gradient end |

## 🔒 Security Features

- **Password Hashing**: bcrypt with salt rounds
- **JWT Tokens**: 7-day expiration
- **Input Validation**: Server-side validation
- **Password Hidden**: Removed from API responses

## 📝 User Schema

```javascript
{
  username: {
    type: String,
    required: true,
    unique: true,
    minlength: 3,
    maxlength: 30
  },
  password: {
    type: String,
    required: true,
    minlength: 6
  },
  createdAt: Date,
  updatedAt: Date
}
```

## 🛠️ Development

### Adding New Fields to User Schema

1. Edit `server/models/User.js`
2. Add field with validation
3. Update routes if needed
4. Update frontend forms

### Building for Production

```bash
# Build React app
cd client
npm run build

# The build folder can be served by Express
# or deployed to static hosting
```

## 📄 License

MIT License - feel free to use this project for learning or as a starter template.

---

Built with 🌿 serenity in mind
"# instaview" 
