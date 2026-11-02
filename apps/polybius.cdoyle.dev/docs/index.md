# Polybius

-{{% import 'icons.html' as icons %}}-

| <nbsp> {: .hide-th } |                                         |
| -------------------- |-----------------------------------------|
| **Group/Version**    | -{{ app_group }}-/-{{ app_api_version }}-   |
| **Supported OS**     | -{{ supported_os_versions() }}-  |
| **Catalog**          | [cdoyle-pdx/eda-catalog][manifest] |

[manifest]: https://github.com/cdoyle-pdx/eda-catalog/tree/main/apps/polybius.cdoyle.dev

Polybius is an arcade game styled after the 1981 cabinet that supposedly appeared in a Portland arcade and
was never seen again. Ten game modes rotate without warning; a terminal interrogates the player about
networking between runs; things get stranger the longer you play.

Open **Polybius → Play Polybius** in the EDA menu and select the game tile. The game signs in as the
logged-in EDA user with no prompt. Scores go on a shared leaderboard, and each user's achievements and
progress are saved to their own profile, so they follow the player to any browser.

/// tab | Resources

<div class="grid" markdown>
<div markdown>

* **PolybiusScore**: one finished run, one leaderboard entry
* **PolybiusProfile**: one EDA user's achievements and progress

</div>
<div markdown>

* **PolybiusConfig**: optional operator settings (namespaces, board size, defaults, test controls)

</div>
</div>
///

/// tab | Views
<div class="grid" markdown>
<div markdown>

* **Play Polybius**: launch tile, the score table and the profile table

</div>
</div>
///

## Where things are kept

| What | Resource | Default namespace |
|---|---|---|
| Leaderboard | `PolybiusScore`, one per recorded run | `eda` (`scoreNamespace`) |
| Achievements, unlocks, play time | `PolybiusProfile`, one per EDA user | `eda` (`profileNamespace`) |
| Settings | `PolybiusConfig`, optional, name it `default` | `eda` |

Scores and profiles are ordinary EDA resources: every save is a transaction, so they are revision-controlled
and can be reverted or deleted like any other resource. To clear the board, delete the `PolybiusScore`
resources. To reset one player, delete their `PolybiusProfile`.

The player name on a score is what the player typed at the end of the run (prefilled from the EDA username).
At an event many people often share one login, so the name, not `edaUser`, identifies who played.

## Opened outside EDA

The same page opened anywhere other than EDA's `/core/httpproxy/v1/polybius/` path, or when the browser is
not logged in to EDA, plays standalone and keeps scores in the browser. In the browser console,
`polybius.status()` shows whether the game is linked, as whom, and the last few calls it made.

## Access

Installing the app adds two ClusterRoles: `eda-polybius-player` (read the board, add scores, read the
config, create and update profiles) and `eda-polybius-admin` (everything, including delete).
