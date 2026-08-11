# Romantic Date Invitation — self-hosted

## What it does

- `/` is the romantic invitation.
- Responses are submitted to your own Node/Express server.
- Responses are stored in a local SQLite database.
- `/admin` is your private response dashboard.
- The server does not use a third-party form service.

Only information that the visitor intentionally submits is stored.

## Run locally

1. Install Node.js 20+.
2. Open a terminal in this project folder.
3. Run:

   npm install

4. Set an admin password.

Linux/macOS:
   ADMIN_PASSWORD="your-long-password" npm start

Windows PowerShell:
   $env:ADMIN_PASSWORD="your-long-password"; npm start

5. Open http://localhost:3000/
6. Open http://localhost:3000/admin to view responses.

The database file `responses.db` is created automatically.

## Deploying

A simple option is Render or another Node.js hosting provider that supports persistent disks/volumes.

Build command:
   npm install

Start command:
   npm start

Environment variable:
   ADMIN_PASSWORD = your-long-random-password

IMPORTANT:
SQLite is a file database. On hosts with ephemeral filesystems, responses can disappear on restart/redeploy. Use a persistent disk/volume, or replace SQLite with a hosted database such as PostgreSQL.

## Production security

- Use HTTPS.
- Use a long unique ADMIN_PASSWORD.
- Do not commit `responses.db` or `.env` to Git.
- If the app becomes public, consider adding rate limiting and a stronger admin authentication system.
