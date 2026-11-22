# 🎬 Marquee - Modern Movie Booking System

A full-featured, production-ready movie ticket booking web application with **3D Cinema Seat Selection (Three.js / React Three Fiber)**, **Supabase Cloud Database & Auth (Google OAuth)**, **Razorpay Payment Gateway**, **Live YouTube Cinema Screen Video Streaming**, and a complete **Admin Management Dashboard**.
LIVE APLLICATION" https://dainty-cocada-99dd91.netlify.app/ "
---

## ✨ Features

### 🎟️ Customer Booking Experience
- **Interactive 3D Cinema Seat Selection**:
  - Full 3D auditorium built with **Three.js**, **@react-three/fiber**, and **@react-three/drei**.
  - Orbit, pan, zoom controls, and realistic auditorium lighting.
  - Interactive clickable seats with clean, user-friendly seat numbering (e.g., `K7`, `A12`).
  - **"See the view from this seat"** feature: smoothly animates the camera to preview the exact sightline to the screen before booking.
  - Seamless fallback to 2D classic grid map for older devices or WebGL-disabled environments.
- **Auditorium Screen Video Streaming**:
  - Live YouTube videos streamed directly onto the virtual 3D cinema screen (trailers or theatre screen view links configured by admins).
  - Responsive video playback with full audio/fullscreen controls.
- **Movies Directory & Detail View**:
  - Filter by Genre, Language, Format (2D, 3D, IMAX), and Rating.
  - Official trailer modal and comprehensive movie details (Cast, Director, Duration, Certification).
- **Theatres & Showtimes**:
  - Filter showtimes by date and select preferred auditoriums.
- **Payments & Instant Ticket Confirmation**:
  - Integrated **Razorpay Checkout modal** (UPI, Credit/Debit Cards, Net Banking).
  - Interactive digital ticket with scannable QR code and booking receipt.
  - User booking history under `/my-bookings`.
- **Interactive Notifications**:
  - Notification Bell in the navbar with unread badge indicators.
  - Live alerts for booking confirmations, upcoming show reminders, and 3D features.

### 🛡️ Admin Management Dashboard
- **Analytics & Revenue**:
  - Live occupancy rates, total revenue, bookings count, and interactive charts powered by **Recharts**.
- **Theatres Management**:
  - Add, edit, or delete theatres and auditoriums.
  - **Screen View Link (YouTube)**: Admin can assign any YouTube trailer or video link to a theatre/screen, which streams live in the 3D auditorium during seat selection.
- **Movies & Shows Management**:
  - Add and manage movies (title, poster, backdrop, trailer, duration, genres).
  - Schedule shows with dates, times, prices, and screen selection.
- **Bookings & Users**:
  - Real-time list of all bookings across theatres with cancellation and status toggle controls.
  - User role management (User / Administrator).
- **Admin Notifications**:
  - Live notifications for incoming bookings, order status updates, and system health.

---

## 🛠️ Tech Stack

- **Frontend Framework**: React 18 + Vite + TypeScript
- **Styling**: Tailwind CSS + clsx + tailwind-merge
- **3D Graphics & Animations**: Three.js + @react-three/fiber + @react-three/drei + GSAP
- **Database & Authentication**: Supabase (`@supabase/supabase-js`)
- **Payment Processing**: Razorpay Checkout (`checkout.razorpay.com`)
- **Charts & Data**: Recharts
- **Icons**: Lucide React
- **Routing**: React Router v6
- **Deployment**: Netlify (with SPA `_redirects` and `netlify.toml`)

---

## 🚀 Getting Started

### 1. Prerequisites
- **Node.js** (v18 or higher recommended)
- **npm** or **pnpm** / **yarn**

### 2. Installation
Clone the repository and install dependencies:
```bash
git clone https://github.com/your-username/marquee-movie-booking.git
cd marquee-movie-booking
npm install
```

### 3. Environment Variables
Create a `.env` file in the root directory (or copy from `.env.example`):
```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your-supabase-anon-key
VITE_RAZORPAY_KEY_ID=your-razorpay-key-id
```

### 4. Running Locally
Start the Vite development server:
```bash
npm run dev
```
Open [http://localhost:5173](http://localhost:5173) in your browser.

---

## 📦 Scripts

| Command | Description |
|---|---|
| `npm run dev` | Starts local dev server at `localhost:5173` |
| `npm run build` | Runs TypeScript type check and builds for production to `dist/` |
| `npm run preview` | Previews the production build locally |
| `npm run typecheck` | Runs `tsc --noEmit` to verify TypeScript types |

---

## 🗄️ Database Setup (Supabase)

The project includes SQL migration scripts in:
- [`supabase_schema_changes.sql`](supabase_schema_changes.sql)
- [`supabase/functions/`](supabase/functions/) (Edge functions for Razorpay orders and webhooks)

To configure your own Supabase project:
1. Create a project at [supabase.com](https://supabase.com).
2. Run the SQL schema scripts in the Supabase SQL Editor.
3. Enable Google Auth under **Authentication > Providers > Google** (if Google login is desired).
4. Add your Netlify or localhost URL to **Authentication > URL Configuration > Redirect URLs**.

---

## 🌐 Netlify Deployment

1. Run `npm run build` to generate the production `dist/` folder.
2. The project contains:
   - `public/_redirects`: `/* /index.html 200`
   - `netlify.toml`: build and publish configuration
3. Drag and drop the `dist/` folder (or deployment zip) to [Netlify Drop](https://app.netlify.com/drop), or link your GitHub repo directly to Netlify.
4. Set environment variables `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` in Netlify Site Settings > **Environment variables**.

---

## 📄 License
MIT License. Built for seamless cinematic ticketing.
