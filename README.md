# MERN Authentication Boilerplate

A complete, production-ready authentication system built with the MERN stack (MongoDB, Express.js, React, Node.js).

## 🚀 Features

### Backend
- **User Authentication**: Register, login, logout with JWT tokens
- **Password Management**: Secure password hashing with bcrypt, password reset functionality
- **Role-based Access Control**: User and admin roles with middleware protection
- **Input Validation**: Comprehensive validation using express-validator
- **Security Features**: Helmet.js, CORS, rate limiting, secure headers
- **MongoDB Integration**: Mongoose ODM with optimized schemas and indexing
- **Error Handling**: Centralized error handling and validation
- **API Documentation**: RESTful API with clear endpoint documentation

### Frontend
- **Modern React**: Built with React 18, hooks, and functional components
- **Responsive Design**: Mobile-first design with Tailwind CSS
- **Form Management**: React Hook Form with validation
- **State Management**: Context API for authentication state
- **Protected Routes**: Route protection based on authentication status
- **Toast Notifications**: User feedback with react-hot-toast
- **Icon System**: Consistent iconography with react-icons

## 📁 Project Structure

```
mern-auth-boilerplate/
├── backend/
│   ├── config/
│   │   └── database.js
│   ├── controllers/
│   │   ├── authController.js
│   │   └── userController.js
│   ├── middleware/
│   │   ├── auth.js
│   │   └── validate.js
│   ├── models/
│   │   └── User.js
│   ├── routes/
│   │   ├── auth.js
│   │   └── user.js
│   ├── .env.example
│   ├── package.json
│   └── server.js
├── frontend/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── auth/
│   │   │   │   ├── Login.js
│   │   │   │   ├── Register.js
│   │   │   │   ├── ForgotPassword.js
│   │   │   │   └── ResetPassword.js
│   │   │   ├── common/
│   │   │   │   └── LoadingSpinner.js
│   │   │   ├── dashboard/
│   │   │   │   └── Dashboard.js
│   │   │   ├── layout/
│   │   │   │   └── Navbar.js
│   │   │   └── profile/
│   │   │       ├── Profile.js
│   │   │       ├── ProfileForm.js
│   │   │       └── PasswordForm.js
│   │   ├── contexts/
│   │   │   └── AuthContext.js
│   │   ├── App.js
│   │   ├── index.js
│   │   └── index.css
│   ├── package.json
│   ├── tailwind.config.js
│   └── postcss.config.js
└── README.md
```

## 🛠️ Installation

### Prerequisites
- Node.js (v16 or higher)
- MongoDB (local or Atlas)
- npm or yarn

### Backend Setup

1. **Navigate to backend directory:**
   ```bash
   cd backend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Environment Configuration:**
   ```bash
   cp env.example .env
   ```
   
   Edit `.env` file with your configuration:
   ```env
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/mern-auth
   JWT_SECRET=your-super-secret-jwt-key
   JWT_EXPIRE=7d
   FRONTEND_URL=http://localhost:3000
   ```

4. **Start the server:**
   ```bash
   # Development mode
   npm run dev
   
   # Production mode
   npm start
   ```

### Frontend Setup

1. **Navigate to frontend directory:**
   ```bash
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm start
   ```

The frontend will run on `http://localhost:3000` and automatically proxy API requests to the backend.

## 🔐 API Endpoints

### Authentication Routes (`/api/auth`)

| Method | Endpoint | Description | Access |
|--------|----------|-------------|---------|
| POST | `/register` | User registration | Public |
| POST | `/login` | User login | Public |
| GET | `/me` | Get current user | Private |
| POST | `/refresh` | Refresh JWT token | Private |
| POST | `/logout` | User logout | Private |
| POST | `/forgot-password` | Request password reset | Public |
| POST | `/reset-password` | Reset password with token | Public |

### User Routes (`/api/user`)

| Method | Endpoint | Description | Access |
|--------|----------|-------------|---------|
| GET | `/profile` | Get user profile | Private |
| PUT | `/profile` | Update user profile | Private |
| PUT | `/change-password` | Change password | Private |
| GET | `/:id` | Get user by ID | Public |
| GET | `/search` | Search users | Public |
| DELETE | `/deactivate` | Deactivate account | Private |
| GET | `/admin/all` | Get all users | Admin |
| PUT | `/admin/:id/role` | Update user role | Admin |

## 🎨 Frontend Features

### Authentication Flow
- **Login/Register**: Clean, responsive forms with validation
- **Protected Routes**: Automatic redirection for unauthenticated users
- **Persistent Sessions**: JWT tokens stored in localStorage
- **Password Reset**: Complete forgot password workflow

### User Dashboard
- **Profile Overview**: User statistics and account information
- **Quick Actions**: Easy access to common tasks
- **Responsive Design**: Works seamlessly on all devices

### Profile Management
- **Tabbed Interface**: Organized sections for different settings
- **Form Validation**: Real-time validation with helpful error messages
- **Password Security**: Secure password change with current password verification

## 🔒 Security Features

- **JWT Authentication**: Secure token-based authentication
- **Password Hashing**: bcrypt with salt rounds
- **Input Validation**: Server-side validation for all inputs
- **Rate Limiting**: Protection against brute force attacks
- **CORS Configuration**: Secure cross-origin requests
- **Helmet.js**: Security headers and protection
- **Role-based Access**: Admin and user role management

## 🚀 Deployment

### Backend Deployment
1. Set production environment variables
2. Use PM2 or similar process manager
3. Configure MongoDB Atlas or production database
4. Set up reverse proxy (Nginx)

### Frontend Deployment
1. Build the production bundle: `npm run build`
2. Deploy to Vercel, Netlify, or your preferred hosting
3. Update backend CORS settings with production frontend URL

## 🧪 Testing

The boilerplate includes testing setup for both frontend and backend:

```bash
# Backend tests
cd backend
npm test

# Frontend tests
cd frontend
npm test
```

## 📝 Environment Variables

### Backend (.env)
```env
PORT=5000
NODE_ENV=development
MONGODB_URI=mongodb://localhost:27017/mern-auth
JWT_SECRET=your-super-secret-jwt-key
JWT_EXPIRE=7d
FRONTEND_URL=http://localhost:3000
```

### Frontend
- Proxy configuration in `package.json` for development
- Environment variables can be added as needed

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Support

If you encounter any issues or have questions:

1. Check the existing issues
2. Create a new issue with detailed information
3. Include your environment details and error logs

## 🔄 Updates

This boilerplate is actively maintained. Check for updates regularly to get the latest security patches and features.

---

**Happy Coding! 🎉**

