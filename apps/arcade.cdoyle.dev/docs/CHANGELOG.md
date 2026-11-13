# Changelog

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
