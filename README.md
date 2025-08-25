# Flickart (Flipkart Clone) — MERN E‑Commerce

A full‑stack e‑commerce application built with the MERN stack. It showcases core storefront features (browse, search, filter, cart, wishlist), secure checkout with Stripe, and an admin area for product and order management.

## Features

- **Auth & Authorization**: Register/Login with JWT, role‑based access (user/admin)
- **Product Catalog**: Categories, search, filters, product details with reviews
- **Wishlist & Cart**: Add/remove, save for later, shipping flow
- **Checkout**: Stripe Checkout session integration
- **Orders**: User order history, status tracking; admin order management
- **Admin**: Create/update/delete products, seller products view
- **Media & Storage**: Cloudinary for images
- **Responsive UI**: React 18, Vite, Tailwind CSS, MUI components

## Tech Stack

- **Frontend**: React 18, Vite, React Router v6, Tailwind CSS, MUI, Axios
- **Backend**: Node.js, Express, Mongoose, JSON Web Tokens, Cloudinary, Stripe
- **Database**: MongoDB

## Quick Start

### 1) Clone
```sh
git clone https://github.com/aashish-dhiman/E-Commerce.git
cd E-Commerce
```

### 2) Environment Variables
Create `.env` files as described below.

Backend (`backend/.env`):
```dotenv
PORT=8080
MONGODB_URI=YOUR_MONGODB_URI
JWT_SECRET=YOUR_RANDOM_SECRET
CLOUD_NAME=YOUR_CLOUDINARY_CLOUD_NAME
CLOUD_API_KEY=YOUR_CLOUDINARY_API_KEY
CLOUD_SECRET=YOUR_CLOUDINARY_SECRET
STRIPE_SECRET_KEY=YOUR_STRIPE_SECRET_KEY
```

Frontend (`client/.env`):
```dotenv
VITE_API=http://localhost:8080
VITE_STRIPE_PUBLISH_KEY=YOUR_STRIPE_PUBLISHABLE_KEY
VITE_STRIPE_SECRET_KEY=YOUR_STRIPE_SECRET_KEY
# Base server URL without trailing slash, e.g. https://e-commerce-mgtd.onrender.com
VITE_SERVER_URL=YOUR_SERVER_BASE_URL
```

### 3) Install & Run (Dev)
Open two terminals or use the concurrent script.

Option A — run both with one command (from `backend/`):
```sh
cd backend
npm install
npm run dev
```
This starts: `node server.js` and `vite` in the client (`http://localhost:5173`).

Option B — run separately:
```sh
# Backend
cd backend
npm install
npm run server

# Frontend
cd ../client
npm install
npm run dev
```

Visit the app at `http://localhost:5173`.

## Test Users

- **User**
  - Email: `test@test.com`
  - Password: `test123`
- **Admin**
  - Email: `store@flipkart.com`
  - Password: `admin123`

## NPM Scripts

Backend (`backend/package.json`):
- `start`: start backend
- `server`: start backend in watch mode (nodemon)
- `client`: start client dev server
- `dev`: run backend and client together (concurrently)
- `build`: build client and re‑install backend deps

Frontend (`client/package.json`):
- `dev`: Vite dev server
- `build`: build for production
- `preview`: preview production build

## Project Structure

```
E-Commerce/
  backend/
    config/        # DB connection
    controllers/   # auth, product, user
    middleware/    # auth guards
    models/        # mongoose schemas
    routes/        # express routers
    server.js      # app entry
  client/
    src/           # React app (components, pages, routes, context)
    index.html
```

## Notes

- To serve the built client from Express in production, uncomment the static serving lines in `backend/server.js` and run the backend `build` script.
- Ensure Cloudinary and Stripe keys are valid for media upload and checkout.

## Contributing

PRs and issues are welcome! If you find a bug or have an improvement, open an issue or submit a pull request.
