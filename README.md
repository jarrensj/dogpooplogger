# Dog Poop Logger

A web application to help dog owners track and log their dog's bathroom habits. Simple, user-friendly interface to record poop logs with timestamps, view them on a calendar, and manage dog profiles.

> **Note:** This project is currently a Work In Progress (WIP).

## Features

### Poop Logging
- **One-Click Logging** - Log poop events instantly with automatic timestamps
- **Advanced Mode** - Log past events with custom date and time selection
- **Delete Logs** - Remove individual entries with confirmation

### Dog Management
- **Dog Profiles** - Create and manage profiles for your dogs
- **Profile Settings** - Update or delete dog profiles from the settings page

### Calendar View
- **Interactive Calendar** - Visual overview of logged events
- **Date Highlighting** - Days with logs are highlighted in green
- **Date Selection** - Click any date to view logs for that day

### Statistics
- **Monthly Stats** - View total number of poops logged in the current month

### User Experience
- **Responsive Design** - Works on mobile and desktop
- **Client-Side Caching** - Fast loading with 30-day cache for data
- **Secure Authentication** - User accounts powered by Clerk

## Tech Stack

- **Framework:** Next.js 15 (App Router)
- **Language:** TypeScript
- **Styling:** Tailwind CSS 4
- **UI Components:** Radix UI, Lucide Icons
- **Database:** Supabase (PostgreSQL)
- **Authentication:** Clerk
- **Analytics:** Vercel Analytics

## Getting Started

### Prerequisites

- Node.js 18+
- npm, yarn, pnpm, or bun
- Supabase account
- Clerk account

### Environment Variables

Copy `.env.example` to `.env.local` and fill in your credentials:

```bash
cp .env.example .env.local
```

Required variables:
- `NEXT_PUBLIC_SUPABASE_URL` - Your Supabase project URL
- `NEXT_PUBLIC_SUPABASE_ANON_KEY` - Your Supabase anonymous key
- `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY` - Your Clerk publishable key
- `CLERK_SECRET_KEY` - Your Clerk secret key

### Installation

```bash
# Install dependencies
npm install

# Run development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to see the app.

### Database Setup

Run the SQL migrations in the `migrations/` folder in order:

1. `001_initial_schema.sql` - Creates the poops table
2. `002_add_dogs_table.sql` - Creates the dogs table
3. `003_add_dog_id_to_poops.sql` - Adds dog relationship to poops

## Project Structure

```
dogpooplogger/
├── app/
│   ├── api/           # API routes for dogs and poops
│   ├── settings/      # Settings page
│   ├── layout.tsx     # Root layout
│   └── page.tsx       # Main dashboard
├── components/        # React components
├── hooks/             # Custom React hooks
├── lib/               # Utilities and clients
├── migrations/        # Database migrations
└── utils/             # Helper functions
```

## Deployment

Deploy easily on [Vercel](https://vercel.com):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new)

Make sure to configure your environment variables in the Vercel dashboard.
