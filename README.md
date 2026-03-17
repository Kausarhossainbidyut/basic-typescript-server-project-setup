# TypeScript Express MongoDB Starter

A production-ready TypeScript backend starter template with Express.js and MongoDB. Clone this repo to quickly bootstrap new projects.

## Features

- TypeScript with strict mode
- Express.js with middleware setup
- MongoDB connection with Mongoose
- JWT authentication ready
- Bcrypt password hashing
- CORS enabled
- Environment configuration with dotenv
- Error handling (404 & global error handler)
- Health check endpoint

## Quick Start

### 1. Clone the Repository

```bash
git clone <your-repo-url> my-new-project
cd my-new-project
```

### 2. Update Project Info

Edit `package.json` to update your project name and description:

```json
{
  "name": "my-new-project",
  "version": "1.0.0",
  "description": "Your project description here",
  "author": "Your Name"
}
```

### 3. Install Dependencies

```bash
npm install
```

### 4. Setup Environment Variables

Create a `.env` file in the root directory:

```env
PORT=5000
MONGO_CONNECTION_STRING=mongodb://127.0.0.1:27017/your_database_name
BCRYPT_SALT_ROUNDS=12
JWT_SECRET=your_super_secret_key
JWT_EXPIRES_IN=7d
GEMINI_API_KEY=your_gemini_api_key
CLIENT_URL=http://localhost:3000
```

### 5. Run the Development Server

```bash
npm run dev
```

Server will start at `http://localhost:5000`

## Available Scripts

| Script | Description |
|--------|-------------|
| `npm run dev` | Start development server with hot reload |
| `npm run build` | Compile TypeScript to JavaScript |
| `npm start` | Run compiled production build |

## Project Structure

```
.
├── src/
│   ├── config/
│   │   └── db.ts          # Database & environment config
│   ├── app.ts             # Express app setup
│   └── server.ts          # Server entry point
├── dist/                  # Compiled JavaScript (auto-generated)
├── .env                   # Environment variables (create this)
├── .gitignore
├── package.json
├── tsconfig.json
└── README.md
```

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Health check - returns server status |

## Next Steps

After cloning, you can:

1. **Add Routes**: Create `src/routes/` folder and add your API routes
2. **Add Models**: Create `src/models/` folder for Mongoose schemas
3. **Add Controllers**: Create `src/controllers/` folder for business logic
4. **Add Middleware**: Create `src/middleware/` folder for auth, validation, etc.

### Example: Adding a New Route

```typescript
// src/routes/user.route.ts
import { Router } from 'express';
const router = Router();

router.get('/users', (req, res) => {
  res.json({ message: 'Get all users' });
});

export default router;
```

Then import in `app.ts`:

```typescript
import userRoutes from './routes/user.route';
app.use('/api/v1', userRoutes);
```

## Tech Stack

- **Runtime**: Node.js
- **Language**: TypeScript
- **Framework**: Express.js
- **Database**: MongoDB (Mongoose)
- **Authentication**: JWT + Bcrypt

## License

ISC