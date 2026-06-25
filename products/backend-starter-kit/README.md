# Node.js Production Backend Starter Kit
Price: 199 RMB

## Features
- JWT auth (access + refresh tokens)
- Role-based access control (RBAC)
- PostgreSQL/MySQL via Sequelize ORM
- Redis caching layer
- Rate limiting
- Structured logging (Winston)
- Input validation (Joi)
- Global error handling
- Swagger/OpenAPI docs
- Unit tests (Jest + Supertest)
- CI/CD (GitHub Actions)
- Docker + docker-compose
- Environment config management
- Health check endpoint

## Stack
- Node.js 18+ / Express.js
- PostgreSQL 14+ / MySQL 8+
- Redis 6+
- Docker

## Project Structure
src/
  config/      - Config loader (.env)
  middleware/  - Auth, validation, error, logging
  models/      - Sequelize models
  routes/      - Express routes
  controllers/ - Request handlers
  services/    - Business logic
  validators/  - Joi schemas
  utils/       - Helper functions
  tests/       - Jest test suites

## Getting Started
npm install
cp .env.example .env
npm run db:migrate
npm run dev

## API Endpoints
POST /api/auth/register    - User registration
POST /api/auth/login       - User login (returns JWT)
POST /api/auth/refresh     - Refresh access token
POST /api/auth/logout      - Invalidate refresh token
GET  /api/users/me         - Get current user profile
PUT  /api/users/me         - Update profile
GET  /api/users            - List users (admin only)
CRUD /api/[resource]       - Generic resource endpoints
GET  /health               - Health check
GET  /api-docs             - Swagger UI

## Use Cases
- SaaS backend foundation
- REST API microservice
- Mobile app backend
- Admin dashboard API
- Startup MVP
