TaskFlow — Full-Stack Project Management Platform

TaskFlow is a full-stack project and task management web application built with React and Node.js/Express. It provides authentication, project management, task tracking, role-based demo users, dashboard KPIs, and analytics through a REST API.

The application is designed as a portfolio project and runs completely without MySQL or any external database. Backend data is persisted locally using a JSON file.

Features

- JWT-based authentication
- Role-aware users: Admin, Manager, and Member
- Project creation and management
- Task creation and assignment
- Task status management
- Task priorities and due dates
- Dashboard KPIs
- Project and task analytics
- RESTful API architecture
- Local JSON data persistence
- Responsive UI for desktop, tablet, and mobile
- Client-server architecture using React and Express

Tech Stack

Frontend
- React
- Vite
- JavaScript
- HTML5
- CSS3

Backend
- Node.js
- Express.js
- REST API
- JWT
- bcryptjs
- CORS

Architecture

text
TaskFlow
│
├── React + Vite Frontend
│        │
│        │ HTTP / REST API
│        ▼
├── Node.js + Express Backend
│        │
│        ├── JWT Authentication
│        ├── Project APIs
│        ├── Task APIs
│        └── Analytics APIs
│
└── Local JSON Storage
         └── server/src/data/store.json

Project Structure

text
taskflow/
│
├── client/
│   ├── src/
│   │   ├── main.jsx
│   │   └── styles.css
│   ├── index.html
│   ├── package.json
│   └── vite.config.js
│
├── server/
│   ├── src/
│   │   ├── index.js
│   │   └── store.js
│   ├── .env.example
│   └── package.json
│
├── .gitignore
└── README.md

Getting Started

Prerequisites

Make sure you have installed:

- Node.js
- npm
- Git

No MySQL installation is required.

1. Clone the repository

bash
git clone https://github.com/yourusername/taskflow.git
cd taskflow

2. Install and run the backend

Open a terminal:

```bash
cd server
npm install
npm run dev
```

The API will run at:

text
http://localhost:5000

You can verify the backend using:

text
http://localhost:5000/api/health

3. Install and run the frontend

Open a second terminal:

bash
cd client
npm install
npm run dev

Open the URL displayed by Vite, normally:

text
http://localhost:5173

Demo Credentials

The project includes demo users for testing.

| Role | Email | Password 
| Admin | admin@taskflow.dev | Taskflow@123 
| Manager | manager@taskflow.dev | Taskflow@123 
| Member | member@taskflow.dev | Taskflow@123 

API Overview

Authentication

text
POST /api/auth/login
GET  /api/me

Users

```text
GET /api/users
```

Projects

text
GET  /api/projects
POST /api/projects

Tasks

text
GET   /api/tasks
POST  /api/tasks
PATCH /api/tasks/:id

Analytics

text
GET /api/analytics

Health Check

text
GET /api/health

Data Persistence

TaskFlow automatically creates its local data store when the backend starts.

text
server/
└── src/
    └── data/
        └── store.json


This allows projects, tasks, and users to persist between application restarts without requiring a database server.

This JSON-based storage approach is intended for portfolio demonstration and local development. A production implementation would use a database such as MySQL or PostgreSQL with proper transaction and concurrency handling.

Security

The application implements:

- JWT authentication
- Password hashing using bcryptjs
- Protected API routes
- Authentication middleware
- Separation of public and private user data
- Environment-based configuration support

For production deployment, sensitive secrets should be stored using environment variables or a dedicated secret-management solution.

What I Built

This project demonstrates practical full-stack development concepts including:

- Building a React frontend
- Designing REST APIs with Express
- Implementing JWT authentication
- Managing application state
- Creating CRUD-style workflows
- Connecting frontend and backend services
- Implementing role-aware application logic
- Persisting application data
- Building responsive interfaces
- Structuring a maintainable full-stack project

License

This project is available for educational and portfolio purposes.
