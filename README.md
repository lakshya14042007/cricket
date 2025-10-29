# Bid Cricket — Multiplayer bidding + match (Firebase)

## Files
- `index.html` — create/join room, sets starting budget, generates pool
- `game.html` — bidding UI and full match engine (20 overs)
- `firebase-rules.json` — Realtime DB rules (dev)

## Steps to run
1. Create Firebase project (console).
2. Enable **Realtime Database** (choose location) and paste rules from `firebase-rules.json`.
3. Optional: Enable Authentication (Anonymous) if you want secure writes; code currently uses open DB (change rules accordingly).
4. Replace `firebaseConfig` in `index.html` and `game.html` if you have different config.
5. Push repository to GitHub and enable **GitHub Pages** (or use Firebase Hosting).
6. Open `index.html` in browser, create a room, share the same room id with friend.
   - Player 1: Create room (will set pool)
   - Player 2: Join same room id (both will enter bidding)
7. Click a player in pool on either client to open bidding for that player.
   - Both players enter bid amount (must be <= their budget).
   - When both bids received, winner gets player; budget deducted.
   - Repeat until both squads reach team size (default 11).
8. When squads full, click **Force Start Match** or it will auto-set `readyToStart`. Match engine will simulate 20 overs.

## Customization ideas
- Add authentication + user profiles.
- Add timers to bidding rounds.
- Add manual play choices (instead of auto-sim).
- Improve UI/animations.

