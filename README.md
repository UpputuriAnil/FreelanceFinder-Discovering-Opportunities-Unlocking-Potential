# FreelanceFinder - Discovering Opportunities, Unlocking Potential

A comprehensive MERN-based freelance platform designed to connect freelancers with opportunities and help them grow their careers.

## 🎓 Project Information

**Author**: Anil Upputuri  
**Team ID**: LTVIP2026TMIDS78552  
**University**: Mohan Babu University  
**Roll Number**: 23102A010607  

**Project Type**: Internship Project - MERN Stack Development  
**Duration**: [Project Duration]  
**Academic Year**: 2025-2026

**FreelanceFinder** is a full-stack web application that serves as a bridge between freelancers and clients, providing a seamless experience for finding freelance jobs, managing projects, and fostering professional growth. The platform showcases the right opportunities and provides support for career development in the freelance world.

## Tech Stack

### Frontend
- **React.js** - Modern UI framework
- **React Router** - Client-side routing
- **Axios** - HTTP client for API calls
- **Socket.io Client** - Real-time communication
- **React Icons** - Icon library
- **UUID** - Unique identifier generation

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **Socket.io** - Real-time bidirectional communication
- **MongoDB with Mongoose** - Database and ODM
- **bcrypt** - Password hashing
- **CORS** - Cross-origin resource sharing
- **Body Parser** - Request body parsing

## Project Structure

```
FreelanceFinder-Discovering-Opportunities-Unlocking-Potential/
├── Document/                    # Project documentation and reports
├── Project Files/               # Complete source code
│   ├── client/                 # React frontend application
│   └── server/                 # Node.js backend API
├── Video Demo/                 # Project demonstration video
└── README.md                   # This file
```

## 🚀 How to Clone and Run on Your Device

### 📋 Prerequisites

Before you begin, ensure you have the following installed:

#### Required Software
- **Node.js** (v16 or higher) - [Download Node.js](https://nodejs.org/)
- **npm** (comes with Node.js) or **yarn** package manager
- **MongoDB** - Choose one of the following:
  - [MongoDB Community Server](https://www.mongodb.com/try/download/community) (Local installation)
  - [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) (Cloud-based, free tier available)
- **Git** - [Download Git](https://git-scm.com/downloads)

#### Optional but Recommended
- **VS Code** or any code editor
- **MongoDB Compass** (GUI for MongoDB management)
- **Postman** (for API testing)

---

### 🛠️ Step-by-Step Installation Guide

#### Step 1: Clone the Repository

```bash
# Clone the project from your repository
git clone https://github.com/UpputuriAnil/Freelance-Finder-Discovering-Opportunities-Unlocking-Potential.git

# Navigate to the project directory
cd FreelanceFinder-Discovering-Opportunities-Unlocking-Potential
```

#### Step 2: Backend Setup

```bash
# Navigate to the server directory
cd "Project Files/server/server"

# Install all backend dependencies
npm install

# Create environment file
touch .env
```

**Configure the `.env` file** (add these variables):
```env
# Server Configuration
PORT=5000
NODE_ENV=development

# MongoDB Configuration
MONGODB_URI=mongodb://localhost:27017/freelancefinder
# OR for MongoDB Atlas:
# MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/freelancefinder

# JWT Secret (generate a random string)
JWT_SECRET=your-super-secret-jwt-key-here

# CORS Configuration
FRONTEND_URL=http://localhost:3000
```

#### Step 3: Frontend Setup

```bash
# Navigate to the client directory (from project root)
cd "Project Files/client/client"

# Install all frontend dependencies
npm install
```

#### Step 4: Database Setup

**Option A: Local MongoDB**
```bash
# Start MongoDB service (Windows)
net start MongoDB

# OR (macOS/Linux)
sudo systemctl start mongod
```

**Option B: MongoDB Atlas**
1. Create a free account at [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a new cluster
3. Get your connection string
4. Add it to your `.env` file

---

### 🚀 Running the Application

#### Method 1: Run Both Servers Separately (Recommended for Development)

**Terminal 1 - Backend Server:**
```bash
cd "Project Files/server/server"
node index.js
```
You should see: `Server running on port 5000` and `MongoDB connected successfully`

**Terminal 2 - Frontend Server:**
```bash
cd "Project Files/client/client"
npm start
```
This will automatically open http://localhost:3000 in your browser

#### Method 2: Run with Concurrently (Advanced)

Install concurrently globally:
```bash
npm install -g concurrently
```

Create a `start.js` file in the project root with:
```javascript
const { spawn } = require('child_process');
const path = require('path');

// Start backend
const backend = spawn('node', ['index.js'], {
  cwd: path.join(__dirname, 'Project Files/server/server'),
  stdio: 'inherit'
});

// Start frontend
const frontend = spawn('npm', ['start'], {
  cwd: path.join(__dirname, 'Project Files/client/client'),
  stdio: 'inherit'
});

backend.on('close', (code) => {
  console.log(`Backend exited with code ${code}`);
  process.exit(code);
});

frontend.on('close', (code) => {
  console.log(`Frontend exited with code ${code}`);
  process.exit(code);
});
```

Then run:
```bash
node start.js
```

---

### 🌐 Access Points

Once running, you can access:

- **Frontend Application**: http://localhost:3000
- **Backend API**: http://localhost:5000
- **API Documentation**: http://localhost:5000/api-docs (if implemented)

---

### 📱 Device-Specific Instructions

#### Windows Users
```powershell
# Install dependencies using PowerShell
cd "Project Files/server/server"
npm install

cd ..\..\client\client
npm install

# Run servers
cd ..\..\server\server
node index.js

# Open new PowerShell window for frontend
cd "Project Files/client/client"
npm start
```

#### macOS/Linux Users
```bash
# Install dependencies
cd "Project Files/server/server"
npm install

cd ../../client/client
npm install

# Run servers (in separate terminals)
# Terminal 1:
cd "Project Files/server/server"
node index.js

# Terminal 2:
cd "Project Files/client/client"
npm start
```

---

### 🔧 Troubleshooting Common Issues

#### Issue 1: Port Already in Use
```bash
# Find process using port 3000 or 5000
netstat -ano | findstr :3000
# Kill the process
taskkill /PID <PID> /F
```

#### Issue 2: MongoDB Connection Failed
- Check if MongoDB is running
- Verify connection string in `.env`
- Ensure MongoDB service is started

#### Issue 3: Module Installation Errors
```bash
# Clear npm cache
npm cache clean --force

# Delete node_modules and package-lock.json
rm -rf node_modules package-lock.json

# Reinstall
npm install
```

#### Issue 4: CORS Errors
- Ensure `FRONTEND_URL` in `.env` matches your frontend URL
- Check that CORS is properly configured in the backend

---

### 📦 Production Deployment

For production deployment, refer to the project documentation in `/Document/Mern Project Freelancer.pdf` for detailed deployment instructions.

---

## 📋 Key Features

- **User Authentication** - Secure registration and login system
- **Job Discovery** - Browse and search freelance opportunities
- **Real-time Communication** - Live chat and notifications using Socket.io
- **Profile Management** - Create and manage professional profiles
- **Project Tracking** - Monitor ongoing and completed projects
- **Career Growth Tools** - Resources and insights for professional development

## Demo

Watch the project demonstration: [Project Demo Video](https://drive.google.com/file/d/1dq1IH-PKqLJ650Vb2jaB863caGkcWeya/view?usp=drivesdk)

## Documentation

- **Project Report**: Available in the `/Document` folder
- **Technical Documentation**: Included in respective module README files
- **API Documentation**: Available in the server documentation

## Contributing

This project was developed as an internship project showcasing full-stack development skills using the MERN stack.

## License

This project is for educational and demonstration purposes.

---

**Note**: For detailed setup instructions and troubleshooting, please refer to the individual README files in each module directory.
