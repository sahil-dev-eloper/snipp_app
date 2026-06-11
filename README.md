# Snipp

Snipp is a Next.js app for creating, editing, viewing, and deleting code snippets. It uses Prisma with SQLite for persistence and server actions for the main write flows.

## Features

- View all snippets on the home page.
- Create a new snippet from `/snippet/new`.
- View a snippet at `/snippet/[id]`.
- Edit a snippet at `/snippet/[id]/edit`.
- Delete snippets from the app.

## Tech Stack

- Next.js 16 with the App Router
- React 19
- Prisma ORM
- SQLite
- Tailwind CSS 4
- shadcn/ui components

## Getting Started

### 1. Install dependencies

```bash
npm install
```

### 2. Configure the database

This project uses SQLite through Prisma. Make sure your environment provides a `DATABASE_URL` value that points to a local SQLite database file.

### 3. Run Prisma migrations

```bash
npx prisma migrate dev
```

### 4. Start the development server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Available Scripts

- `npm run dev` - start the local development server
- `npm run build` - create a production build
- `npm run start` - start the production server
- `npm run lint` - run ESLint

## Project Structure

- `src/app` - routes, layouts, and pages
- `src/actions` - server actions for snippet mutations
- `src/components` - reusable UI and form components
- `src/lib` - shared utilities and Prisma client setup
- `prisma/schema.prisma` - database schema

## Notes

- Snippet data is stored in the `Snippet` model defined in `prisma/schema.prisma`.
- Server actions revalidate the affected routes after create, update, or delete operations.
