# Task Manager Backend

Production-ready RESTful API for task management with JWT authentication.

## Tech Stack

- Node.js 18+ & Express.js
- MongoDB & Mongoose
- JWT (HTTP-only cookies)
- bcrypt, Helmet, CORS, Rate Limiting

## Quick Start

```bash
npm install
npm run dev
```

Server runs on `http://localhost:5000`

## Environment Variables (.env)

```env
NODE_ENV=development
PORT=5000
MONGO_URI=mongodb://localhost:27017/taskmanager
JWT_SECRET=your-secret-key-change-in-production
JWT_EXPIRE=7d
ENCRYPTION_KEY=your-32-character-encryption-key
FRONTEND_URL=http://localhost:3000
```

## Security Features

✅ Password hashing (bcrypt, 10 rounds)  
✅ JWT in HTTP-only cookies  
✅ Input validation (Joi)  
✅ Rate limiting (100 req/15min)  
✅ NoSQL injection prevention  
✅ CORS configuration  
✅ Helmet security headers

## API Endpoints

### Authentication

```http
POST   /api/auth/register    # Register new user
POST   /api/auth/login       # Login user
POST   /api/auth/logout      # Logout user
GET    /api/auth/me          # Get current user
PUT    /api/auth/profile     # Update profile
PUT    /api/auth/password    # Change password
DELETE /api/auth/account     # Delete account
```

### Tasks (Protected)

```http
GET    /api/tasks            # Get all tasks (with filters)
POST   /api/tasks            # Create task
GET    /api/tasks/:id        # Get single task
PUT    /api/tasks/:id        # Update task
DELETE /api/tasks/:id        # Delete task
GET    /api/tasks/stats      # Get task statistics
```

### Query Parameters

- `page` - Page number (default: 1)
- `limit` - Items per page (default: 10)
- `status` - Filter by status (todo, in-progress, completed)
- `priority` - Filter by priority (low, medium, high)
- `search` - Search in title/description

