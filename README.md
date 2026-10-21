# DDA backend

Existing DDA Desktop backend prepared for Render Free.

Build: `npm ci`
Start: `node server.mjs`
Health: `GET /health`
Rewrite: `POST /rewrite` with JSON `{"text":"Hello","mode":"Fix Grammar"}`.

Set OPENAI_API_KEY only in Render environment secrets. Never commit .env.
Render supplies PORT and an HTTPS onrender.com address.

After deployment, verify health and a real rewrite before replacing API_URL in DDA Desktop src/App.tsx (line 19).

This MVP has no user authentication; anyone with its URL can call rewrite. Add authentication before distributing the app publicly.
