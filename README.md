# UltraSafe Predictor

A private, mobile-responsive football match-analysis web app. The server keeps the football API key out of browser code, protects pages and API endpoints with a password, searches real fixtures by date/team, shows recent completed-match form, ranks available market assessments, and saves analysis history locally on the server.

## Important limitations

- This app does not promise safe or guaranteed bets. The under-4.5 and over-0.5 percentages are averages of each team's returned recent completed fixtures, not calibrated forecasts.
- Markets for first-half substitutions, corners, direct goals from corners, cards/fouls, match result/double chance, and correct score are intentionally marked as requiring more data rather than assigned fabricated probabilities.
- Event labels may not confirm whether a goal was scored directly from a corner. Verify specialist event data independently.
- Fixture coverage, statistics, rate limits and available competitions depend on your API-Football subscription.
- This starter app uses an in-memory login session store and local JSON history. For a public deployment, use HTTPS, a strong password, persistent database storage, and a production-grade authentication/session system. Do not expose it publicly without those hardening steps.

## Run locally

Requires Node.js 18 or newer.

1. Copy `.env.example` to `.env` and set `APP_PASSWORD` and `API_FOOTBALL_KEY`.
2. Export the variables in your shell (Node does not automatically load `.env` without a package):

   **Linux/macOS**
   ```sh
   export APP_PASSWORD='your-long-private-password'
   export API_FOOTBALL_KEY='your-api-football-key'
   npm start
   ```

   **Windows PowerShell**
   ```powershell
   $env:APP_PASSWORD='your-long-private-password'
   $env:API_FOOTBALL_KEY='your-api-football-key'
   npm start
   ```
3. Open `http://localhost:3000`.

## Data provider

Create an API key at API-FOOTBALL / API-Sports and set it only as a server environment variable named `API_FOOTBALL_KEY`. Do not paste the key into `public/app.js` or commit it into source control.

## Deploy for phone and laptop

Deploy the project to a Node.js host that supports environment variables and persistent disk (history.json is written beside server.js). Set `APP_PASSWORD`, `API_FOOTBALL_KEY`, and optionally `PORT` in the host settings. Use the HTTPS deployment URL on both devices. A static-only host will not run this server or protect the API key.
