# Hostinger Deploy (One-Click Setup)

This repo is prepared so Hostinger can deploy it directly from GitHub.

## Build and run commands

- Install command: `npm install`
- Build command: leave empty (or `npm run build`)
- Start command: `npm start`

`postinstall` already runs TypeScript build automatically, so `dist/` is created during deployment.

## Node.js version

Use Node.js `22` (or any `>=20`).

## Environment variables (required)

Set these in Hostinger dashboard:

- `NODE_ENV=production`
- `PORT=3000` (or leave Hostinger default if it injects one)
- `MONGO_URI=...`
- `JWT_SECRET=...`
- `JWT_EXPIRES_IN=7d`
- `ADMIN_EMAIL=...`
- `ADMIN_PASSWORD_HASH=...` (recommended) or `ADMIN_PASSWORD=...`
- `CORS_ORIGINS=https://your-frontend-domain.com`
- `BASE_URL=https://your-api-domain.com`

Optional:

- `IMAGES_BASE_URL=https://your-frontend-domain.com`
- `PUBLIC_API_BASE_URL=https://your-api-domain.com`

## Health check

After deploy, open:

- `https://your-api-domain.com/health`

Expected response:

```json
{"status":"ok"}
```
