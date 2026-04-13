# Workspace

## Overview

pnpm workspace monorepo using TypeScript. Each package manages its own dependencies.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **API framework**: Express 5
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.

## AI Student Guru

A full-featured AI-powered student learning web app for Indian school students (Class 1-12).

### Features

- **Login/Signup**: Mobile number based registration, optional password set by admin
- **Dashboard**: Big colorful feature buttons for all learning tools
- **Learn Topic**: AI explains any topic step-by-step using GPT-5.2
- **Ask Doubt**: Students type questions, AI answers with step-by-step explanation
- **Camera Doubt**: Upload/capture image of question, AI reads and solves it (vision AI)
- **Upload Homework**: Upload homework image, AI provides complete step-by-step solution
- **Voice Doubt**: Use browser speech recognition, send to AI, get text answer
- **Chat History**: Persistent history of all questions/answers grouped by type
- **Admin Panel**: Admin (admin/admin123) can view students and set passwords

### Tech

- **Frontend**: React + Vite at `/` (artifacts/ai-student-guru)
- **Backend**: Express API server at `/api` (artifacts/api-server)
- **AI**: OpenAI GPT-5.2 via Replit AI Integrations (no API key needed)
- **Storage**: JSON files (`students.json`, `history.json`) in api-server working directory
- **Auth**: Simple token-based, stored in localStorage

### Admin Access

- URL: `/admin`
- Default credentials: `admin` / `admin123`
- Can be changed via `ADMIN_USERNAME` and `ADMIN_PASSWORD` env vars
