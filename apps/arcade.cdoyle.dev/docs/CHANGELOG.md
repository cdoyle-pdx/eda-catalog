# Changelog

## v0.1.3

- New `fourWayMode: hold` for 4-way profiles: a diagonal keeps the current
  direction, and the direction changes only on a clean press of a new one.
  Rolling the d-pad between left and right no longer bumps up or down.
  `newest` (the default) behaves as before.
- 4-way switches now release the old direction before pressing the new one,
  so a game never sees two directions held at once.
- Tester: the 4-way checkbox is now a Directions choice (8-way, 4-way newest,
  4-way hold).

## v0.1.2

- Games now pick a pad-specific profile even when the controller was used
  before the shim finished loading. Chrome announces a pad only once, and a
  game that loads the shim after its EDA sign-in could miss it, leaving the
  built-in default in use.
- The console logs every profile change:
  `[arcade-input] <game> uses profile: <name> (pad: ...)`.

## v0.1.1

- Controller Tester: Save to EDA no longer fails with "no token present"
  after the tester has been open a while. The sign-in token is kept until a
  new one arrives, and a missing or expired token triggers one fresh sign-in
  and a retry.

## v0.1.0

- ControllerProfile resource: map gamepad buttons and axes to keyboard keys,
  per game and per controller model (`games`, `padMatch`), with 4-way
  movement, tap-mode keys and an axis deadzone.
- Shared `arcade-input.js` shim, served at
  `/core/httpproxy/v1/gamepad/arcade-input.js` for any EDA app game to load
  under its own CSP.
- Controller Tester: live pad view, learn mode, bindings editor, YAML export
  and Save to EDA.
