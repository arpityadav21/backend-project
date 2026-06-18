# VideoTube Backend

A production-ready REST API for a video streaming platform — built with Node.js, Express, MongoDB, and Cloudinary.

## Tech Stack

- **Node.js + Express.js** — server and routing
- **MongoDB + Mongoose** — database and schemas
- **JWT** — access & refresh token authentication
- **Bcrypt** — password hashing
- **Multer + Cloudinary** — file upload pipeline
- **Cookie-parser, CORS, dotenv**

## Features

- JWT auth with access tokens (1d) + refresh tokens (10d) stored in HTTP-only cookies
- Secure password hashing with bcrypt
- Media uploads via Multer → Cloudinary CDN (only URL stored in DB)
- Centralised error handling with custom `ApiError` + `asyncHandler`
- Clean MVC architecture — routes, controllers, models, utils fully separated

## Project Structure

```
src/
├── controllers/   # Request handling logic
├── db/            # MongoDB connection
├── middlewares/   # Auth, Multer
├── models/        # Mongoose schemas
├── routes/        # API route definitions
└── utils/         # ApiError, ApiResponse, asyncHandler, Cloudinary
```

## Getting Started

```bash
git clone https://github.com/arpityadav21/backend-project.git
cd backend-project
npm install
cp .env.sample .env   # fill in your values
npm run dev
```

## Environment Variables

```env
PORT=8000
MONGODB_URI=your_mongodb_uri
CORS_ORIGIN=*
ACCESS_TOKEN_SECRET=
ACCESS_TOKEN_EXPIRY=1d
REFRESH_TOKEN_SECRET=
REFRESH_TOKEN_EXPIRY=10d
CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
```

## API Routes

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/v1/users/register` | Register with avatar upload |
| POST | `/api/v1/users/login` | Login, receive JWT tokens |
| POST | `/api/v1/users/logout` | Logout, clear cookies |
| POST | `/api/v1/users/refresh-token` | Refresh access token |
| GET | `/api/v1/users/current-user` | Get logged-in user profile |
| PATCH | `/api/v1/users/avatar` | Update avatar |
| PATCH | `/api/v1/users/cover-image` | Update cover image |

---

> Made by [Arpit Yadav] (https://github.com/arpityadav21)