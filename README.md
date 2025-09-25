# Equify - Full Stack Web Application

A modern full-stack web application with:
- **Frontend**: Next.js (deployed on Vercel)
- **Backend**: Node.js/Express API (deployed on Railway)
- **Database**: PostgreSQL (deployed on Railway)

## Project Structure

```
equify/
├── frontend/          # Next.js frontend application
├── backend/           # Node.js/Express API server
├── database/          # Database schemas and migrations
└── README.md
```

## Quick Start

### Prerequisites
- Node.js 18+ 
- PostgreSQL (for local development)
- Git

### Local Development

1. **Setup Backend**
   ```bash
   cd backend
   npm install
   cp .env.example .env
   # Configure your database connection in .env
   npm run dev
   ```

2. **Setup Frontend**
   ```bash
   cd frontend
   npm install
   cp .env.local.example .env.local
   # Configure API endpoint in .env.local
   npm run dev
   ```

3. **Setup Database**
   ```bash
   cd database
   # Run migrations
   psql -U your_user -d your_db -f init.sql
   ```

## Deployment

### Frontend (Vercel)
1. Connect your GitHub repository to Vercel
2. Set build command: `cd frontend && npm run build`
3. Set output directory: `frontend/.next`
4. Configure environment variables in Vercel dashboard

### Backend (Railway)
1. Connect your GitHub repository to Railway
2. Set start command: `cd backend && npm start`
3. Configure environment variables in Railway dashboard
4. Railway will automatically detect the Node.js app

### Database (Railway)
1. Add PostgreSQL service in Railway
2. Use the provided DATABASE_URL in your backend environment variables

## Environment Variables

### Backend (.env)
```
NODE_ENV=development
PORT=8000
DATABASE_URL=postgresql://username:password@localhost:5432/equify
JWT_SECRET=your_jwt_secret_here
CORS_ORIGIN=http://localhost:3000
```

### Frontend (.env.local)
```
NEXT_PUBLIC_API_URL=http://localhost:8000/api
NEXT_PUBLIC_APP_NAME=Equify
```

## API Documentation

The API is documented and available at `/api/docs` when running the backend server.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License

MIT License