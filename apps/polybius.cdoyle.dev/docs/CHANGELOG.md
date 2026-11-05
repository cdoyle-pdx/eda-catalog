# Changelog

## v1.1.0

- Telemetry: the game logs notable moments as `PolybiusEvent` resources (severity on EDA's alarm scale), and a new
  telemetry page tails them for a second screen beside the cabinet. `PolybiusConfig` gains `telemetry` and `eventKeep`.
- The island has a new secret, and the game has a new ending. One new achievement, of a new rank.

## v1.0.0

First release in EDA.

- Signs in silently as the logged-in EDA user (authorization code with PKCE, no prompt).
- Shared leaderboard as `PolybiusScore` resources; crowned players shown in gold.
- Each user's achievements and progress saved to a `PolybiusProfile` and restored in any browser.
- Optional `PolybiusConfig` for score and profile namespaces, board size, default pace and timer, and test controls.
- "Play Polybius" dashboard with the launch tile, score table and profile table.
- Plays standalone with browser storage when opened outside EDA or when not logged in.
