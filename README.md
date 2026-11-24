# FRIENDZONE – Play Together

A React/Vite browser game prototype with Firebase Anonymous Auth + Firestore room/lobby, live player position updates, collectible stars, scoreboard and room chat.

## Firebase setup
1. Create a Firebase project and register a Web app.
2. Authentication → Sign-in method → enable **Anonymous**.
3. Firestore Database → create database.
4. Copy Web app configuration into `.env` (copy `.env.example` first).
5. Publish `firestore.rules` from this project in Firestore Rules.

## Run locally
```bash
npm install
cp .env.example .env
# Fill .env with your Firebase values
npm run dev
```
Open the Vite URL on your computer. For friends on different networks, deploy the app (e.g. Firebase Hosting or another HTTPS host). Share the deployed URL and room code.

## Notes
- Firestore is used for room state and player updates. It is suitable for a simple demo, but it is not a low-latency game networking service; motion may feel delayed at larger scale.
- This is an early prototype. The included rules are a starting point, not production-grade security. They don't enforce an 8-player cap, host authority over game-state fields is broad, and client-side movement/score updates are not cheat-proof. Add trusted server logic, validation, moderation, abuse controls and stronger rules before public deployment.
- Chat is room-only and limited to 160 characters. Don't share personal details in chat.
