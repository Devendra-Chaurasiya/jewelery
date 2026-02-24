# Setup Guide

## Prerequisites

- Node.js 18+
- npm 9+

## Install

```bash
npm install
```

If install fails with file-lock errors on Windows:

1. Close running terminals/processes that may lock `node_modules`
2. Delete `node_modules` and `package-lock.json`
3. Run `npm install` again

## Run Development Server

```bash
npm run dev
```

Vite will print a local URL (usually `http://localhost:5173`).

## Production Build

```bash
npm run build
```

Build output is generated in `dist/`.

## Runtime Configuration

The Studio page includes an **API URL** input. Paste your backend/ngrok base URL there.

Example:

`https://your-id.ngrok-free.app`

The app automatically calls:

`https://your-id.ngrok-free.app/generate_image`

## Common Checks

- Ensure backend is running and reachable
- Ensure CORS is enabled on backend
- Ensure backend returns JSON with `image_base64`