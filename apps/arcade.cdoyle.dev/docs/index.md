# Arcade Controllers

-{{% import 'icons.html' as icons %}}-

| <nbsp> {: .hide-th } |                                         |
| -------------------- |-----------------------------------------|
| **Group/Version**    | -{{ app_group }}-/-{{ app_api_version }}-   |
| **Supported OS**     | -{{ supported_os_versions() }}-  |
| **Catalog**          | [cdoyle-pdx/eda-catalog][manifest] |
| **Source Code**      | <small>coming soon</small>              |

[manifest]: https://github.com/cdoyle-pdx/eda-catalog

Gamepad support for EDA arcade games such as Snake and Polybius. Plug a
controller into the machine running the browser and play with it, without
changing how the game reads input.

Games load a small shared script from this app. The script reads the pad
through the browser's Gamepad API and sends the keyboard keys the game already
understands. ControllerProfile resources decide which button sends which key,
per game and per controller model.

The application provides the following components:

/// tab | Resources

<div class="grid" markdown>
<div markdown>

* ControllerProfile: maps pad buttons and axes to keyboard keys

</div>
</div>
///

/// tab | Dashboards

<div class="grid" markdown>
<div markdown>

* Controller Tester: live pad view, learn mode, profile editor, Save to EDA

</div>
</div>
///

## Getting started

1. Install **Arcade Controllers** from the catalog.
2. Plug in a controller. On the Retro-Bit Sega pad, hold **START + B for 5
   seconds** to switch it to X-Input mode.
3. Open **Arcade Controllers → Controller Tester**, select **VIEW**, and press
   any button on the pad.
4. Select **Learn all**, set the game name and select **Save to EDA**.

Without any profile, games use a built-in layout for standard X-Input pads.

## Access

| Role | Grants |
|---|---|
| `eda-gamepad-reader` | Read profiles, which players need for their profile to apply |
| `eda-gamepad-admin` | Create, edit and delete profiles |

Games can grant read access in their own player role instead. See the
integration guide.

## Adding controller support to a game

See the integration guide, served by the app at
`/core/httpproxy/v1/gamepad/INTEGRATING.html` and linked from the tester.
