# Johnnwa Tech Global — Solar E-Commerce Platform

A full-featured solar equipment e-commerce website for Johnnwa Tech Global Ltd, a Lagos-based solar energy company serving Nigeria.

## Features

- **Product Catalog** — Browse inverters, batteries, solar panels, charge controllers, and all-in-one systems with filtering by category and brand
- **Product Comparison** — Compare up to 4 products side-by-side within the same category
- **Solar Calculator** — Right-size a solar system based on appliances and usage patterns
- **Shopping Cart** — Add products, adjust quantities, and send orders via WhatsApp
- **Powerpreneur Program** — Affiliate/referral system where partners register, get approved, share a referral link, and track their referrals and commissions in a dashboard
- **Blog** — Admin-managed blog posts published via Supabase
- **Admin Dashboard** — Hidden admin panel at `/admin` for managing powerpreneurs, referrals, submissions, and blog posts
- **Contact Form** — Submissions stored in Supabase
- **Responsive Design** — Mobile-first with a bottom tab bar on mobile and full nav on desktop

## Tech Stack

- **Frontend**: React + Vite + Tailwind CSS
- **Backend**: Supabase (PostgreSQL, Edge Functions, RLS)
- **Icons**: lucide-react

## Environment Variables

Copy `.env.example` to `.env` and fill in your Supabase credentials:

```
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

## Getting Started

```bash
npm install
npm run dev
```

Build for production:

```bash
npm run build
```

## Project Structure

- `src/johnnwa-site.jsx` — Main application (single-file SPA)
- `src/lib/db.js` — Data access layer (Supabase + Edge Function calls)
- `src/lib/supabaseClient.js` — Supabase client initialization
- `supabase/migrations/` — Database migrations (tables, RLS policies)
- `supabase/functions/jtg-admin/` — Edge Function for admin and Powerpreneur auth
- `public/images/` — Product and project images organized by brand/category

## Admin Access

Navigate to `/admin` or append `?view=admin` to the URL. The admin password is configured in the Edge Function.

## Powerpreneur Flow

1. User registers on the Powerpreneurs page (name, email, phone, location, role, password)
2. Admin approves the registration in the admin dashboard
3. Approved Powerpreneur logs in and gets a referral link + code
4. When a visitor arrives via `?ref=CODE`, the click is tracked
5. Admin manually creates referrals and sets commission amounts
6. Powerpreneur sees stats, referrals list, and earnings in their dashboard

## License

Proprietary — Johnnwa Tech Global Ltd
