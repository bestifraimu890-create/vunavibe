# Vunavibe

A university-focused social networking frontend — built with React, React Router, and
localStorage as a mock backend. No server required.

## Getting started

```bash
npm install
npm run dev
```

Then open the printed local URL (usually http://localhost:5173).

## Trying it out

- The app starts with a clean slate — no seed users, posts, communities, or events. Create an
  account from **Create account** on the login screen to get started.
- Everything you do — posts, likes, comments, connection requests, joined communities, messages,
  saved posts, event RSVPs — is saved to your browser's localStorage, so it survives a refresh.
- Open the app in a second private/incognito window and sign up as a different student to try
  messaging, connecting, and liking posts between two accounts on the same machine.

## Project structure

```
src/
  components/   reusable UI pieces (PostCard, Sidebar, ChatWindow, etc.)
  pages/        one file per route/page
  context/      AppContext.jsx — all app state + interactions, persisted to localStorage
  data/         mockData.js — gradient/faculty/level constants + empty seed arrays
  utils/        storage.js — localStorage + small formatting helpers
  styles/       theme.css (tokens), base.css, layout.css, components.css, pages.css
```

## Notes for adding a real backend later

`src/context/AppContext.jsx` is the single place all reads/writes happen. Every action
(`createPost`, `sendFriendRequest`, `sendMessage`, etc.) is already isolated there — swapping
the `useState` + localStorage persistence for real API calls should not require touching any
page or component.
