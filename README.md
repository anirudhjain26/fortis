# Fortis — [Live Website](https://fortis-cs316.vercel.app/)

[Video Demo](https://drive.google.com/file/d/1p9XE3jujp8zljiyNqBsaE-LCwwNtyD5i/view?usp=sharing)

Fortis is a full-stack fitness web application designed to help users log workouts, track progress, connect with workout partners, and stay accountable. It combines features from popular apps like Strong and Strava into one cohesive platform, offering a seamless experience for fitness enthusiasts.

## Features

### Profile & Authentication
- Google sign-in via Auth0
- User profiles with customizable details: name, age, height, weight, unit preferences (metric/imperial), and privacy settings
- Option to delete account and all associated data

### Workout Logging
- Add, edit, and delete exercises with sets, reps, weights, and notes
- Filter exercises by location and muscle group
- “Quick Add” feature for your 10 most recent exercises
- Persistent workout sessions saved across refreshes

### Workout History & Analytics
- View and sort past workouts by week
- Weekly recaps with charts and summaries by muscle group
- Streak tracking with GitHub-style calendar visualization
- Visual intensity indicators for each workout session

### Discover Templates
- Browse and filter public workout templates by popularity and muscle group
- Save templates or use them directly in your next session
- Share templates with friends or publicly

### Social Features
- Matcher Tool: Find workout partners based on gym location, availability, and fitness goals
- Friends list with friend requests and search functionality
- Leaderboard based on total sets completed

## Tech Stack

- Frontend: Next.js (React)
- Backend: Python Flask (via Next.js API routes)
- Database: PostgreSQL (hosted on Vercel)
- Authentication: Auth0 with Google OAuth
- Deployment: Vercel

## Testing & Data Generation

We created and tested the platform with 5,000 synthetic users using Python and Mockaroo. The test data included realistic workouts, progression patterns, gym availability, and activity levels. All functionality was validated with scaled data before migrating to a limited production environment.

## File Structure

```
fortis/
│
├── api/
│   └── index.py
│
├── app/
│   ├── favicon.ico
│   ├── globals.css
│   ├── layout.tsx
│   └── page.tsx
│
├── components/
│   ├── SearchBarComponents/
│   ├── SocialSearchBarComponents/
│   └── ...
│
├── pages/
│   ├── _app.js
│   ├── discover.tsx
│   ├── friends.tsx
│   ├── history.tsx
│   ├── ...
│
├── public/
│   ├── animated/
│   ├── images/
│   └── ...
│
├── queries/
│   ├── CurrentTable.sql
│   ├── InsertAuth.sql
│   └── ...
│
├── test_data/
│   ├── activities.csv
│   ├── generate_workouts.py
│   └── ...
│
├── next.config.js
├── package.json
├── pnpm-lock.yaml
├── postcss.config.js
├── requirements.txt
├── tailwind.config.js
└── tsconfig.json
```

## Getting Started

### Prerequisites
- Node.js and pnpm installed
- Vercel CLI for deployment and environment management

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/anirudhjain26/fortis.git
   cd fortis
   ```

2. Install dependencies:
   ```bash
   pnpm install
   ```

3. Set up PostgreSQL:
   - Install the Vercel Postgres package:
     ```bash
     pnpm i @vercel/postgres
     ```
   - Link the project to Vercel:
     ```bash
     vercel link
     ```
   - Pull the latest environment variables:
     ```bash
     vercel env pull .env.development.local
     ```

4. Set up additional dependencies:
   ```bash
   pnpm add @auth0/nextjs-auth0 pg cookies-next react-select
   ```

5. Start the development server:
   ```bash
   pnpm dev
   ```

   Open [http://localhost:3000](http://localhost:3000) to view the app. The Flask server will run on [http://127.0.0.1:5328](http://127.0.0.1:5328).

## Deployment

The app is deployed on Vercel, with the Flask server hosted as [Python serverless functions](https://vercel.com/docs/concepts/functions/serverless-functions/runtimes/python). PostgreSQL is also hosted on Vercel and linked to the project.

### Challenges
We encountered deployment roadblocks, such as running out of free Vercel and DBMS trials, but successfully overcame them to deliver a scalable and functional product.

### Related Repositories
- [Original Repo](https://github.com/jess-che/fortis)
- [Second Repo](https://github.com/Meeeee6623/fortis)

## Helpful Documentation

- [Next.js Documentation](https://nextjs.org/docs)
- [Flask Documentation](https://flask.palletsprojects.com/en/1.1.x/)
- [Vercel Documentation](https://vercel.com/docs)

