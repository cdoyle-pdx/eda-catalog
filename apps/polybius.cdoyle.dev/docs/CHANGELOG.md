# Changelog

## v1.0.0

First release in EDA.

- Signs in silently as the logged-in EDA user (authorization code with PKCE, no prompt).
- Shared leaderboard as `PolybiusScore` resources; crowned players shown in gold.
- Each user's achievements and progress saved to a `PolybiusProfile` and restored in any browser.
- Optional `PolybiusConfig` for score and profile namespaces, board size, default pace and timer, and test controls.
- "Play Polybius" dashboard with the launch tile, score table and profile table.
- Plays standalone with browser storage when opened outside EDA or when not logged in.
