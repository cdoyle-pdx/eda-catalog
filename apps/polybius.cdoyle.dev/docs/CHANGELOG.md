# Changelog

## v1.5.0

- Fabric Crawl is a packet-delivery game: an RJ45 plug carries UCast, BCast and MCast packets from SRC to DST through
  a spine, across a more maze-like fabric with traffic flowing on the links. At Force V a firewall fails open onto a
  border leaf (BLeaf-1 or BLeaf-2); reaching it brings a system query, and a hit while it is open patches it shut and
  drops you to Force IV.
- Flatland: twice the height range and more width, wide height barriers (over, under, through), an altimeter, and a
  retro-synth sky.
- Packet Snake steers in absolute directions.
- Tube boost and brake animate the ship and recharge for 5 s, with a meter.
- The level break's accuracy figure is labelled with a different, unexplained metric each time.

## v1.4.0

- The Air Strike is three stages, each with its own enemies and boss: Open Water (a flying switch with PAM4, then
  DWDM, lasers), Night Raid (searchlights, flak, night fighters, mine layers, jammers; an IPv4 packet as a train, one
  attack per header field), and The Burning Ground (a lava field, corrupted enemies, IT).
- 1941/1943-style pickups: weapon canisters (3-WAY, AUTO, SHOTGUN, LASER, SUPER SHELL), side fighters, and a repair
  pinwheel after each boss.
- Developer mode select on the title and pause screens (`[` and `]`, with the test controls showing).
- God mode: the Konami code on the pause screen. It is also in the Morse rotation.
- Four new achievements.

## v1.3.0

- Two ways to play, fixed for the whole game when it starts (Settings: Pace). **Arcade** is the full game: a system
  query every 2-3.5 minutes, a mode change every 90-145 s, achievements on. **Booth** is the show-floor cabinet: a
  query every 1-2 minutes, a mode change every 60-90 s, achievements off (bar one).
- System queries (interrogations) now come only on that timer, judged against whatever state you are in when they
  arrive. Reaching Force V, spinning, not firing and pausing no longer trigger one. The one exception: reaching Force V
  inside an isolated mode still brings its query at once. The separate interrogation timer setting is gone.
- Damage is harsher: any hit drops you straight to Force I (from ROOT too), and a hit at Force I ends the game.
- The island has a far shore past the runway, with a hammock. Booth jams the fire-pit lock and leaves the plane
  unfuelled; the hammock is the Booth ending, with a silver crown. In Arcade, beat IT in the Air Strike and the plane
  lands back on the island, IT's kill mark under the cockpit; the far shore is the Arcade ending, with a gold crown.
- Crowned names are shown in gold or silver. `PolybiusScore` gains an optional `crown` field (`gold` or `silver`).
- The plane is now a WWII Pacific fighter, on the island and in the Air Strike.
- Four new achievements. `PolybiusConfig.defaultWindow` is no longer used.

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
