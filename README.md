# HydroBuddy — Hydration Tracker

A responsive, browser-based edition of HydroBuddy inspired by the original Android project documentation. Built with vanilla HTML, CSS and JavaScript so it can be deployed as a static site on Vercel, Netlify, or Replit without a build step.

## Features
- Local demo account creation and login
- Profile settings and an editable daily hydration goal
- Goal suggestion based on weight and activity level (wellness estimate, not medical advice)
- Quick-add buttons (150 ml, 250 ml, 500 ml) and custom intake
- Daily progress ring, remaining intake, weekly summary and charts
- Daily, weekly and monthly history views
- Delete entries and export logs to CSV
- Reminder interval and waking-hour settings, browser notifications and test reminder
- Light and dark themes
- Responsive desktop and mobile layout
- Local persistence using `localStorage`

## Run locally
Open `index.html` in a browser, or serve this folder with any static web server. No package installation required.

## Deploy on Vercel
1. Create a GitHub repository named `hydrobuddy` and upload the contents of this folder (the files should be at the repository root).
2. Sign in to Vercel and choose **Add New → Project**.
3. Import the `hydrobuddy` repository.
4. Framework preset: **Other**. Build command: leave empty. Output directory: `.` (root). Install command: leave empty.
5. Click **Deploy**. Add the resulting HTTPS URL to your portfolio.

Alternative: import/upload the folder into Replit as a static HTML/CSS/JS project and publish it.

## Important implementation notes
This is a portfolio-friendly web adaptation, not a Kotlin APK. The original Android Room Database and WorkManager have been replaced by browser `localStorage` and in-tab reminder checks. Browser reminders only run while the app is open and may be throttled by the browser; this version does not promise background notifications when the tab/browser is closed. Notification support requires HTTPS (Vercel provides this) and browser permission.

Authentication is a local demo mechanism. Passwords and records are stored in this browser and are **not suitable for real user accounts or sensitive information**. Data does not sync between browsers/devices. For a production multi-user app, add a backend such as Supabase/Firebase with secure authentication and a database, plus a service worker/push notification implementation.

Hydration recommendations vary by individual. The goal estimator is a simple starting estimate, not medical advice.
