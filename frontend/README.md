# Frontend (React + Vite)

This is the client app for the E‑Commerce Store. For complete setup instructions (env, backend, dev and prod), see the repository root `README.md`.

Quick dev commands:

```bash
# from repo root
npm run dev            # start backend (http://localhost:5000)
npm run dev:client     # start frontend (http://localhost:5173)
```

Notes:
- The frontend expects the API at `http://localhost:5000/api` in development. Adjust in `frontend/src/lib/axios.js` if you change the backend port.
- If `http://127.0.0.1:5173` does not open, use `http://localhost:5173` (Vite listens on IPv6 ::1 by default).
