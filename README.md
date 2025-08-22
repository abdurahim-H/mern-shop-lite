<h1 align="center">E-Commerce Store 🛒</h1>

![Demo App](/frontend/public/screenshot-for-readme.png)

[Video Tutorial on Youtube](https://youtu.be/sX57TLIPNx8)

About This Course:

-   🚀 Project Setup
-   🗄️ MongoDB & Redis Integration
-   💳 Stripe Payment Setup
-   🔐 Robust Authentication System
-   🔑 JWT with Refresh/Access Tokens
-   📝 User Signup & Login
-   🛒 E-Commerce Core
-   📦 Product & Category Management
-   🛍️ Shopping Cart Functionality
-   💰 Checkout with Stripe
-   🏷️ Coupon Code System
-   👑 Admin Dashboard
-   📊 Sales Analytics
-   🎨 Design with Tailwind
-   🛒 Cart & Checkout Process
-   🔒 Security
-   🛡️ Data Protection
-   🚀Caching with Redis
-   ⌛ And a lot more...

## Local setup (no Docker)

### 1) Create .env in repo root

```bash
PORT=5000
MONGO_URI=your_mongo_uri

UPSTASH_REDIS_URL=your_redis_url

ACCESS_TOKEN_SECRET=your_access_token_secret
REFRESH_TOKEN_SECRET=your_refresh_token_secret

CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

STRIPE_SECRET_KEY=your_stripe_secret_key
CLIENT_URL=http://localhost:5173
NODE_ENV=development
```

Notes:
- Only MongoDB is required to run locally. Redis/Cloudinary/Stripe are optional; related features are skipped until keys are provided.
- `CLIENT_URL` must match the dev server origin (Vite default is `http://localhost:5173`).

### 2) Install dependencies

```bash
# from repo root
npm install
cd frontend && npm install && cd ..
```

### 3) Start in development (two terminals)

Terminal A (backend on http://localhost:5000):
```bash
npm run dev
```

Terminal B (frontend on http://localhost:5173):
```bash
npm run dev:client
```

If port 5173 is not reachable at 127.0.0.1, use http://localhost:5173 (Vite listens on IPv6 ::1 by default).

### 4) Production build + run

```bash
# Build frontend then start backend (serves frontend/dist in production)
npm run build
npm run start
```

### Health checks / quick verification

- Frontend: open `http://localhost:5173` (dev) or backend `http://localhost:5000` after `npm start` (prod)
- API examples (require login for protected routes):
  - `GET http://localhost:5000/api/products` → 401 until authenticated
  - `GET http://localhost:5000/api/analytics` → 401 until authenticated
  - Sign up / sign in via the UI to obtain cookies and re-try

### Troubleshooting

- Mongo not running: ensure `mongod` is installed and started (or use a MongoDB Atlas URI in `MONGO_URI`).
- Vite dev server not opening on 127.0.0.1: use `http://localhost:5173`.
- Port conflicts: change `PORT` in `.env` and update `frontend/src/lib/axios.js` baseURL if you change backend port in dev.
- Missing external keys: Cloudinary/Stripe/Redis features will be disabled; core app still runs.

