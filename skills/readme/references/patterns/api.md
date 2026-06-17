# Pattern: API / Backend Service

Use for Express, Fastify, Hono, FastAPI, Django, Gin, Axum projects — anything that primarily serves HTTP endpoints.

---

## Section Order

1. Title + description + badges
2. Features / capabilities
3. Requirements / prerequisites
4. Getting started (local setup)
5. Environment variables
6. API reference (endpoints table)
7. Authentication (if applicable)
8. Testing
9. Deployment
10. Contributing
11. License

---

## Template

```markdown
# APP-NAME — keyword description

Short description. What it does, what technology it's built on, what makes it notable (performance, features, design).

[![Build](https://img.shields.io/github/actions/workflow/status/OWNER/REPO/ci.yml)](https://github.com/OWNER/REPO/actions)
[![License](https://img.shields.io/github/license/OWNER/REPO)](LICENSE)

## Features

- ✅ Feature one — one sentence
- ⚡️ Feature two — one sentence
- 🔑 Feature three — one sentence
- 📦 Feature four — one sentence

## Requirements

- RUNTIME VERSION (e.g., Node.js 20+, Python 3.11+, Go 1.22+)
- DATABASE (e.g., PostgreSQL 15+)
- [Other external dependencies]

## Getting Started

**1. Clone:**
```bash
git clone https://github.com/OWNER/REPO.git
cd REPO
```

**2. Install dependencies:**
```bash
npm install
```

**3. Configure environment:**
```bash
cp .env.example .env
```

**4. Set up database:**
```bash
npm run db:migrate
npm run db:seed    # optional
```

**5. Start the server:**
```bash
npm run dev       # development (with hot reload)
npm start         # production
```

Server runs at `http://localhost:PORT`.

## Environment Variables

| Variable | Required | Default | Description |
|---|---|---|---|
| `PORT` | ❌ | `3000` | HTTP server port |
| `DATABASE_URL` | ✅ | — | Database connection string |
| `JWT_SECRET` | ✅ | — | Secret for JWT signing |
| `NODE_ENV` | ❌ | `development` | `development` or `production` |

## API Reference

Base URL: `http://localhost:3000` (development) · `https://api.example.com` (production)

### Authentication

All protected routes require `Authorization: Bearer <token>` header.

Get a token:
```bash
curl -X POST http://localhost:3000/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email": "user@example.com", "password": "password"}'
```

### Endpoints

#### Users

| Method | Endpoint | Auth | Description |
|---|---|---|---|
| `GET` | `/users` | ✅ | List users |
| `GET` | `/users/:id` | ✅ | Get user by ID |
| `POST` | `/users` | ❌ | Create user |
| `PUT` | `/users/:id` | ✅ | Update user |
| `DELETE` | `/users/:id` | ✅ Admin | Delete user |

**POST /users — Request body:**
```json
{
  "email": "user@example.com",
  "password": "password",
  "name": "Display Name"
}
```

**Response:**
```json
{
  "id": "uuid",
  "email": "user@example.com",
  "name": "Display Name",
  "createdAt": "2024-01-01T00:00:00Z"
}
```

#### [Other resource group]

| Method | Endpoint | Auth | Description |
|---|---|---|---|
| `GET` | `/resource` | ✅ | Short description |

## Error Responses

All errors follow this format:
```json
{
  "error": "Error message",
  "code": "ERROR_CODE",
  "status": 400
}
```

| Status | Meaning |
|---|---|
| `400` | Bad request — invalid input |
| `401` | Unauthorized — missing or invalid token |
| `403` | Forbidden — insufficient permissions |
| `404` | Not found |
| `500` | Internal server error |

## Testing

```bash
npm test                    # run all tests
npm run test:unit           # unit tests only
npm run test:integration    # integration tests (requires database)
npm run test:coverage       # with coverage report
```

## Deployment

**Docker:**
```bash
docker build -t APP-NAME .
docker run -p 3000:3000 --env-file .env APP-NAME
```

**Docker Compose:**
```bash
docker-compose up -d
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE)
```

---

## Key rules for API READMEs

1. **Every endpoint in a table.** Method + path + auth required + description.
2. **Request/response bodies with real JSON examples** — from actual route definitions, not invented.
3. **Error format documented.** All HTTP status codes the API returns.
4. **Authentication flow is a first-class section.** Never bury it.
5. **Local setup must work in 5 commands or fewer.**
6. **Environment variables with type (required vs optional) and defaults.**
7. **If OpenAPI/Swagger exists, link to it prominently.**
