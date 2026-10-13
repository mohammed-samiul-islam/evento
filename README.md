# Evento

Event discovery web app for browsing upcoming events by city, built with Next.js, Prisma and PostgreSQL.

**Live demo:** https://evento-sooty.vercel.app/

## Features

- Search form to find events by city; `/events` redirects to `/events/all`
- City pages (`/events/[city]`) listing events sorted by date, paginated 6 per page
- Event detail pages (`/event/[slug]`) with dynamically generated Open Graph images
- Loading skeletons, custom error and not-found pages
- Privacy policy and terms pages
- Prisma seed script for sample event data

## Tech Stack

Next.js (App Router) · TypeScript · React · Tailwind CSS · Prisma · PostgreSQL · Zod · Framer Motion · Radix Icons

## Project Structure

```
prisma/
  schema.prisma     # EventoEvent model
  seed.ts
src/
  app/              # routes: /, /events/[city], /event/[slug], legal pages
  components/       # header, footer, event-card, events-list, pagination, search-form, skeletons
  lib/              # db client, types, data helpers (getEvents, getEvent)
  middleware.ts     # /events -> /events/all
```

## Getting Started

```bash
npm install            # also runs `prisma generate`
npx prisma db push     # create schema in your database
npx prisma db seed     # optional: load sample events
npm run dev
```

Other scripts: `npm run build`, `npm run start`, `npm run lint`.

### Environment Variables

| Name | Purpose |
|------|---------|
| `POSTGRES_PRISMA_URL` | Pooled PostgreSQL connection string |
| `POSTGRES_URL_NON_POOLING` | Direct PostgreSQL connection string |
