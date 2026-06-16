# Bet Terminal Cloud App

This folder is the cloud-ready version of the sports bet tracker. Your original local tracker remains in `../7.html`.

## What This Version Does

- Keeps the same terminal dashboard and bet tracker UI.
- Adds email/password account login through Supabase.
- Syncs bets, settings, bankroll transactions, cashouts, charts, and records to one private cloud row per user.
- Still works in local mode until Supabase keys are added.

## Supabase Setup

1. Go to Supabase and create a free project.
2. Open the project, then open the SQL editor.
3. Paste and run everything from `supabase-schema.sql`.
4. Go to Project Settings, then API.
5. Copy the Project URL.
6. Copy the anon public key.
7. Paste both values into `config.js`.

`config.js` should look like this after setup:

```js
window.BET_TERMINAL_CONFIG = {
  supabaseUrl: "https://your-project-ref.supabase.co",
  supabaseAnonKey: "your-anon-public-key"
};
```

## Test Locally

Open `index.html` in your browser. If Supabase is configured, the Cloud Account bar will let you sign in or create an account.

When you sign in for the first time, the app will upload the local browser data into your cloud account if the cloud account is empty.

## Deploy Later

When local login works, deploy the contents of this folder to Vercel or Netlify. The Supabase anon key is designed to be public; the row-level security rules in `supabase-schema.sql` protect each user's data.
