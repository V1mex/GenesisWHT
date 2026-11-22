# GenesisWHT

A single-file web application (`index.html`) for tracking work shifts, overtime, employer payouts, expenses, recurring bills, and savings goals, powered by **Supabase**.

## Features

- **Today** — log today's shift, track weekly hours, gross earnings, overtime (OT) hours, hours remaining until OT, and estimated net take-home pay after tax.
- **History** — view all logged shifts grouped by work week with total hours, earnings, and ability to add or edit past shifts.
- **Money** — track how much your employer owes you, log received payments, categorized one-time expenses, and monthly recurring bills.
- **Plan** — set savings goals with progress bars and estimated shifts needed, plus weekly/monthly/yearly income and expense overviews.
- **Settings** — configure base hourly rate, OT threshold and rate, estimated tax rate, work week start day, starting balance owed, custom expense categories, or reset your data.
- **Authentication** — sign in or sign up via **Supabase Auth** (Email + password and/or Google OAuth) with per-user data isolation.

## Quick Setup

1. Create a new project on [Supabase](https://supabase.com/) and run `setup.sql` in the **SQL Editor** to create the tables and Row Level Security (RLS) policies.
2. Enable **Data API** and configure your auth providers in **Authentication → Providers** (Email and/or Google).
3. Open `index.html` and replace `YOUR_SUPABASE_URL` and `YOUR_SUPABASE_ANON_KEY` with your project's **Project URL** and public **anon / publishable key** from **Project Settings → API**.
4. Push `index.html` to your repository and enable **GitHub Pages** (or serve it locally via any HTTP server, e.g. `python -m http.server 8000`).

## Security Notes

- Only expose your public `anon` / publishable key in `index.html` — never put your `service_role` key or PostgreSQL database password in client-side code.
- Ensure **Row Level Security (RLS)** is enabled on all tables so users can only access and modify their own rows (`auth.uid() = user_id`).

## License

This project is licensed under the **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)** license — see the [LICENSE](LICENSE) file for 
details.
