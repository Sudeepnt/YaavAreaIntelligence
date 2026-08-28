# Yaav Area Intelligence

Standalone Sangeetha store intelligence map, with nationwide store discovery, map search, editable store pins, proximity tools, and saved area boundaries.

## Run locally

```bash
npm install
npm run dev
```

Open `http://127.0.0.1:8000/sangeetha-map/`.

## Configuration

Copy `.env.example` to `.env` and configure:

- `NEXT_PUBLIC_GOOGLE_MAPS_API_KEY`
- `NEXT_PUBLIC_GOOGLE_MAPS_MAP_ID`
- `GOOGLE_PLACES_API_KEY`
- `SUPABASE_URL`
- `SUPABASE_PUBLISHABLE_KEY`
- `SUPABASE_SERVICE_ROLE_KEY`

For Vercel, configure the same environment variables in the project settings. Google Maps browser-key referrer restrictions must include the deployed domain.

## Database

Run these scripts in the target Supabase project:

1. `supabase-sangeetha-stores.sql`
2. `supabase-sangeetha-store-areas.sql`

## Store catalog

`npm run stores:discover` retrieves and reconciles the nationwide Sangeetha store catalog. `npm run stores:migrate` loads that catalog into Supabase.

The browser map reads cached store data from Supabase. Google Places and Supabase service-role keys are server-only and must never be exposed to the browser.
