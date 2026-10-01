# BharatFlow AI
From Civic Complaints to Civic Intelligence.

## What is in this folder
- `index.html` — the live app: citizen portal and authority console (single file, no build step).
- `demo-prototype.html` — the earlier all-in-one demo with simulated data (clearly labelled as demo).
- `presentation/` — the Build with Bharat 4.0 slide deck.

## index.html: what it does
- Sign-in gateway for citizens and officers (name, email or Indian mobile number, State/UT or department).
- Citizens report problems (type, description, State/UT, locality, severity, photo, optional GPS).
- Authorities see a priority queue with an explainable 0–100 score (severity 30, safety risk 30, report density 15, location impact 15, complaint age 10), then assign, start work and mark resolved.
- Citizens give feedback on completed work; "not fixed" reopens the complaint.
- Solved-problems feed (posts and reels mode) with State/UT filter, names (opt-in), before/after photos and likes.

## Running it
- Open `index.html` in a browser: it runs in single-tab memory mode, so data is lost on refresh and is not shared.
- Shared, live storage (database, photo uploads, account identity) works only when the page is published on claude.ai as an Artifact, because it uses that platform's runtime (`claude.use("db" | "assets" | "user")`).

## Honest limits
- No real password login, email/SMS one-time codes or password reset. Those need a backend (for example Node.js + Express + MongoDB with an email/SMS provider).
- Email/phone are format-checked only, not verified.
- Role separation is enforced in the page, not by the database.
- No AI vision or forecasting in the live app; priority is a transparent formula. The demo prototype's AI and risk forecast are simulated.

## Suggested production stack
React + Vite + Tailwind, Node.js + Express, MongoDB + Mongoose, JWT auth, OTP via an SMS/email service, an image store, and a configurable AI provider.
