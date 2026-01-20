# Vintive Studio - Backend API

FastAPI backend for Vintive Studio website.

## Tech Stack
- FastAPI
- MongoDB (Motor)
- Python 3.11+
- Uvicorn

## Local Development

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Create `.env` file:
```
MONGO_URL=mongodb://localhost:27017
DB_NAME=vintive_studio
CORS_ORIGINS=http://localhost:3000
```

3. Start development server:
```bash
uvicorn server:app --reload --host 0.0.0.0 --port 8001
```

## Deployment to Render.com

1. Push this code to GitHub
2. Go to [render.com](https://render.com)
3. Create new Web Service
4. Connect your GitHub repository
5. Configure:
   - Name: vintive-backend
   - Environment: Python 3
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `uvicorn server:app --host 0.0.0.0 --port $PORT`
6. Add Environment Variables:
   - `MONGO_URL`: Your MongoDB Atlas connection string
   - `DB_NAME`: vintive_studio
   - `CORS_ORIGINS`: Your Vercel frontend URL
7. Deploy!

## Environment Variables

- `MONGO_URL`: MongoDB connection string (required)
- `DB_NAME`: Database name (default: vintive_studio)
- `CORS_ORIGINS`: Allowed CORS origins (comma-separated)

## API Endpoints

- `GET /api/`: Health check
- `POST /api/status`: Create status check
- `GET /api/status`: Get all status checks

## MongoDB Setup (Atlas - Free Tier)

1. Go to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create free account and cluster
3. Click "Connect" → "Connect your application"
4. Copy connection string
5. Replace `<password>` with your password
6. Use this as `MONGO_URL` environment variable

Example connection string:
```
mongodb+srv://username:password@cluster.mongodb.net/?retryWrites=true&w=majority
```

## Project Structure

```
backend/
├── server.py          # Main FastAPI application
├── requirements.txt   # Python dependencies
├── .env.example      # Environment variables template
└── render.yaml       # Render.com configuration
```

## License

MIT
