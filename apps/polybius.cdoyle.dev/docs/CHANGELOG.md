# Changelog

## v1.2.0

- Progression rebuilt around the interrogations, per game: every game starts in Tube Run with only the tube
  variants; Force V plus a correct answer grants ROOT and unlocks a non-tube mode; ROOT plus a correct answer breaks
  open an isolated mode, which joins the rotation if you reach Force V in it without a hit; all three open unlock the
  Duel.
- Force V added below ROOT. ROOT now lasts until you are hit, pulses with the music, and makes every mode harder.
- The Duel reworked: IT changes the rules after each of your clean points, rages at the sixth (into the Dungeon),
  dismisses you if it has scored, and re-isolates everything if it beats you at Force I.
- Mirror mode replaced by Backwards. A clearer voice on the Mountain King crash.

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
