# 🔐 User Authentication System

> **A robust, production-ready authentication API built with Node.js, Express, and MongoDB**

![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)

---

## ✨ Why Choose This System?

### 🛡️ **Enterprise-Grade Security**
- **BCrypt Password Hashing** - Your users' passwords are encrypted with industry-standard bcrypt (10 salt rounds)
- **JWT Token Authentication** - Secure, stateless authentication with 1-hour token expiration
- **Token Storage in Database** - Full control over active sessions with token revocation on logout
- **Middleware Protection** - Routes are guarded with token verification middleware

### ⚡ **Performance & Scalability**
- **Async/Await Architecture** - Non-blocking operations for maximum throughput
- **MongoDB Integration** - NoSQL database optimized for high-performance user management
- **Token Auto-Expiry** - Automatic cleanup of expired tokens (1 hour TTL)
- **Efficient Password Comparison** - Promise-based bcrypt operations

### 🎯 **Complete CRUD Operations**
- ✅ Create new users with automatic password hashing
- ✅ Read all users or get current session user
- ✅ Update user information dynamically
- ✅ Delete users securely

### 🚀 **Developer-Friendly**
- **Clean MVC Architecture** - Separated controllers, models, services, and routes
- **RESTful API Design** - Intuitive endpoint structure
- **Comprehensive Error Handling** - Proper status codes and error messages
- **Easy Integration** - JSON-based request/response format

---

## 📋 Features at a Glance

| Feature | Description | Status |
|---------|-------------|--------|
| 🔑 User Registration | Create account with encrypted password | ✅ Ready |
| 🔓 Login System | JWT-based authentication | ✅ Ready |
| 🚪 Logout | Token revocation on logout | ✅ Ready |
| 👤 User Profile | Get current authenticated user info | ✅ Ready |
| 📝 User Management | Full CRUD operations | ✅ Ready |
| 🔒 Protected Routes | Middleware-based route protection | ✅ Ready |
| ⏰ Token Expiration | Auto-expiring sessions (1 hour) | ✅ Ready |

---

## 🏗️ Project Structure

```
User-Authentication-System/
│
├── 📁 controllers/
│   ├── authController.js      # Login & logout logic
│   ├── userController.js      # CRUD operations
│   └── sessionController.js   # Current user info
│
├── 📁 models/
│   ├── User.js               # User schema with pre-save hashing
│   └── AuthToken.js          # Token storage schema
│
├── 📁 services/
│   ├── authService.js        # JWT generation
│   └── bcryptService.js      # Password hashing/comparison
│
├── 📁 middleware/
│   └── verifyToken.js        # JWT verification middleware
│
├── 📁 routes/
│   ├── authRoutes.js         # /api/auth endpoints
│   ├── userRoutes.js         # /api/users endpoints
│   └── sessionRoutes.js      # /api/session endpoints
│
├── 📁 db/
│   └── db.js                 # MongoDB connection
│
└── server.js                 # Entry point (Port 3010)
```

---

## 🚀 Quick Start

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or cloud instance)

### Installation

```bash
# Clone the repository
git clone https://github.com/majoymajo/User-Authentication-System.git

# Navigate to project directory
cd User-Authentication-System

# Install dependencies
npm install

# Start the server
npm start
```

The server will run on `http://localhost:3010` 🎉

---

## 📡 API Endpoints

### Authentication Routes (`/api/auth`)

#### 🔓 Login
```http
POST /api/auth/login
Content-Type: application/json

{
  "email": "user@example.com",
  "contraseña": "yourPassword"
}
```

**Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

#### 🚪 Logout
```http
POST /api/auth/logout
Authorization: Bearer <your_token>
```

---

### User Management Routes (`/api/users`)

#### 👥 Get All Users
```http
GET /api/users
```

#### ➕ Create User
```http
POST /api/users
Content-Type: application/json

{
  "nombre": "John Doe",
  "edad": 25,
  "email": "john@example.com",
  "contraseña": "securePassword123"
}
```

#### ✏️ Update User
```http
PUT /api/users/:id
Content-Type: application/json

{
  "nombre": "Jane Doe",
  "edad": 26
}
```

#### ❌ Delete User
```http
DELETE /api/users/:id
```

---

### Session Routes (`/api/session`)

#### 👤 Get Current User
```http
GET /api/session/current
Authorization: Bearer <your_token>
```

---

## 🔒 Security Highlights

### Password Protection
- Passwords are **never stored in plain text**
- BCrypt hashing happens automatically via Mongoose pre-save hooks
- 10 salt rounds ensure strong encryption

### Token Management
- JWT tokens are signed with a secure secret key
- Tokens expire after 1 hour
- Stored in database for logout functionality
- Middleware verification protects sensitive routes

### Email Uniqueness
- Email field has `unique: true` constraint
- Prevents duplicate accounts

---

## 🎓 Learning Highlights

This project demonstrates:

✅ **Modern JavaScript** - ES6+ syntax with promises and async operations  
✅ **RESTful API Design** - Proper HTTP methods and status codes  
✅ **Database Modeling** - Mongoose schemas with validation  
✅ **Authentication Flow** - Complete login/logout cycle  
✅ **Middleware Pattern** - Reusable token verification  
✅ **Service Layer** - Separation of business logic  
✅ **Error Handling** - Comprehensive try-catch and promise rejection handling  

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **Express.js** | Web framework for building REST APIs |
| **MongoDB** | NoSQL database for user storage |
| **Mongoose** | ODM for MongoDB |
| **bcrypt** | Password hashing library |
| **jsonwebtoken** | JWT creation and verification |

---

## 🤝 Contributing

Contributions are welcome! Feel free to:
- 🐛 Report bugs
- 💡 Suggest new features
- 🔧 Submit pull requests

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👨‍💻 Author

**majoymajo**  
GitHub: [@majoymajo](https://github.com/majoymajo)

---

## 🌟 Show Your Support

If you find this project useful, please give it a ⭐ on GitHub!

---

<p align="center">
  <strong>Built with ❤️ and JavaScript</strong>
</p>

<p align="center">
  <sub>Secure • Scalable • Simple</sub>
</p>
