# 💬 Talkative - Real-time Chat Application

A modern, full-stack real-time chat application built with React, Node.js, Socket.IO, and MongoDB. Features secure authentication, file sharing, online status tracking, and a beautiful responsive UI.

![Talkative Screenshot](frontend/public/screenshot-for-readme.png)

## ✨ Features

- **Real-time Messaging**: Instant message delivery with Socket.IO
- **User Authentication**: Secure JWT-based authentication with bcrypt password hashing
- **Image Sharing**: Upload and share images with Cloudinary integration
- **Online Status**: See who's online in real-time
- **Profile Management**: Update profile pictures and user information
- **Responsive Design**: Beautiful UI that works on desktop and mobile
- **Modern UI**: Built with Tailwind CSS and DaisyUI components
- **Theme Support**: Multiple theme options for personalization  
- **Message History**: Persistent chat history stored in MongoDB
- **File Upload**: Support for image attachments in conversations

## 🛠️ Tech Stack

### Frontend

- **React 18** - Modern UI library with hooks
- **Vite** - Fast build tool and development server
- **Tailwind CSS** - Utility-first CSS framework
- **DaisyUI** - Tailwind CSS component library
- **Zustand** - Lightweight state management
- **React Router** - Client-side routing
- **Axios** - HTTP client for API requests
- **Socket.IO Client** - Real-time communication
- **React Hot Toast** - Beautiful toast notifications
- **Lucide React** - Beautiful icons

### Backend

- **Node.js** - JavaScript runtime
- **Express.js** - Web framework
- **Socket.IO** - Real-time bidirectional communication
- **MongoDB** - NoSQL database
- **Mongoose** - MongoDB object modeling
- **JWT** - JSON Web Tokens for authentication
- **bcryptjs** - Password hashing
- **Cloudinary** - Image storage and optimization
- **Cookie Parser** - Parse HTTP cookies
- **CORS** - Cross-origin resource sharing

## 🚀 Quick Start

### Prerequisites

- Node.js (v16 or higher)
- MongoDB database
- Cloudinary account (for image uploads)

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/AnkitMishra2006/talkative.git
   cd talkative
   ```

2. **Install dependencies**

   ```bash
   # Install root dependencies
   npm install

   # Install backend dependencies
   cd backend && npm install

   # Install frontend dependencies
   cd ../frontend && npm install
   ```

3. **Environment Setup**

   Create a `.env` file in the `backend` directory:

   ```bash
   cd backend
   cp .env.sample .env
   ```

   Update the `.env` file with your configuration:

   ```env
   PORT=8080
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret_key
   CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
   CLOUDINARY_API_KEY=your_cloudinary_api_key
   CLOUDINARY_API_SECRET=your_cloudinary_api_secret
   NODE_ENV=development
   ```

4. **Start the application**

   **Development mode:**

   ```bash
   # Start backend (from backend directory)
   cd backend
   npm run dev

   # Start frontend (from frontend directory, in a new terminal)
   cd frontend
   npm run dev
   ```

   **Production build:**

   ```bash
   # From root directory
   npm run build
   npm start
   ```

5. **Access the application**
   - Frontend: http://localhost:5173 (development)
   - Backend API: http://localhost:8080 (development)

## 📁 Project Structure

```
talkative/
├── backend/                    # Backend server
│   ├── src/
│   │   ├── controllers/       # Route controllers
│   │   │   ├── auth.controllers.js
│   │   │   └── message.controller.js
│   │   ├── lib/              # Utility libraries
│   │   │   ├── cloudinary.js # Cloudinary configuration
│   │   │   ├── db.js         # Database connection
│   │   │   └── socket.js     # Socket.IO setup
│   │   ├── middleware/       # Express middleware
│   │   │   └── auth.middleware.js
│   │   ├── models/           # Database models
│   │   │   ├── message.model.js
│   │   │   └── user.model.js
│   │   ├── routes/           # API routes
│   │   │   ├── auth.routes.js
│   │   │   └── message.routes.js
│   │   ├── seeds/            # Database seeders
│   │   │   └── user.seed.js
│   │   ├── utils/            # Utility functions
│   │   │   └── utils.js
│   │   └── index.js          # Server entry point
│   ├── .env.sample           # Environment variables template
│   └── package.json
├── frontend/                  # React frontend
│   ├── src/
│   │   ├── components/       # React components
│   │   │   ├── skeletons/    # Loading skeletons
│   │   │   ├── AuthImagePattern.jsx
│   │   │   ├── ChatContainer.jsx
│   │   │   ├── ChatHeader.jsx
│   │   │   ├── MessageInput.jsx
│   │   │   ├── Navbar.jsx
│   │   │   ├── NoChatSelected.jsx
│   │   │   └── Sidebar.jsx
│   │   ├── pages/            # Page components
│   │   │   ├── HomePage.jsx
│   │   │   ├── LoginPage.jsx
│   │   │   ├── ProfilePage.jsx
│   │   │   ├── SettingsPage.jsx
│   │   │   └── SignUpPage.jsx
│   │   ├── store/            # Zustand stores
│   │   │   ├── useAuthStore.js
│   │   │   ├── useChatStore.js
│   │   │   └── useThemeStore.js
│   │   ├── lib/              # Utility libraries
│   │   │   ├── axios.js      # Axios configuration
│   │   │   └── utils.js      # Utility functions
│   │   ├── constants/        # App constants
│   │   │   └── index.js
│   │   ├── App.jsx           # Main App component
│   │   └── main.jsx          # React entry point
│   ├── public/               # Static assets
│   └── package.json
└── package.json              # Root package.json
```

## 🔧 API Endpoints

### Authentication

- `POST /api/auth/signup` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `GET /api/auth/check` - Check authentication status
- `PUT /api/auth/update-profile` - Update user profile

### Messages

- `GET /api/messages/users` - Get all users for sidebar
- `GET /api/messages/:id` - Get messages with specific user
- `POST /api/messages/send/:id` - Send message to user

## 🎨 UI Features

- **Dark/Light Theme**: Toggle between different themes
- **Responsive Layout**: Works seamlessly on mobile and desktop
- **Real-time Updates**: Messages appear instantly without refresh
- **Online Indicators**: See which users are currently online
- **Message Status**: Visual feedback for message delivery
- **Image Previews**: View images directly in chat
- **Emoji Support**: Send and receive emojis in messages
- **Loading States**: Smooth loading animations and skeletons

## 🔐 Security Features

- **JWT Authentication**: Secure token-based authentication
- **Password Hashing**: bcrypt for secure password storage
- **Protected Routes**: Middleware to protect authenticated routes
- **Input Validation**: Server-side validation for all inputs
- **CORS Configuration**: Proper cross-origin resource sharing setup
- **Cookie Security**: HTTP-only cookies for token storage

## 🚀 Deployment

### Environment Variables for Production

```env
NODE_ENV=production
PORT=8080
MONGO_URI=your_production_mongodb_uri
JWT_SECRET=your_strong_jwt_secret
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

### Build for Production

```bash
npm run build
```

This will:

1. Install all dependencies
2. Build the frontend for production
3. Serve the built frontend from the backend server

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the ISC License.

## 👨‍💻 Author

**Ankit Mishra**

- GitHub: [@AnkitMishra2006](https://github.com/AnkitMishra2006)

## 🙏 Acknowledgments

- [React](https://reactjs.org/)
- [Socket.IO](https://socket.io/)
- [Tailwind CSS](https://tailwindcss.com/)
- [DaisyUI](https://daisyui.com/)
- [Cloudinary](https://cloudinary.com/)
- [MongoDB](https://www.mongodb.com/)

## 📞 Support

If you have any questions or need help with setup, please open an issue on GitHub.

---

⭐ **Star this repository if you found it helpful!**
