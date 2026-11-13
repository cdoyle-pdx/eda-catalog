---
resource_name: ControllerProfile
resource_name_plural: controllerprofiles
resource_name_plural_title: Controller Profiles
resource_name_acronym: CP
crd_path: docs/arcade.cdoyle.dev/crds/arcade.cdoyle.dev_controllerprofiles.yaml
# 'auto-crd' will automatically select between the normal resource and workflow icon
icon: auto-crd
---

# Controller Profile

-{{% import 'icons.html' as icons %}}-

-{{ category(resource_name_plural) }}- → -{{ icons.circle(letter=resource_name_acronym, text=resource_name_plural_title) }}-

A ControllerProfile maps gamepad inputs (`button:N`, `axis:N+`, `axis:N-`) to
keyboard keys for EDA arcade games. Browsers read it and no intent reconciles
it. A profile can live in any namespace, because games find profiles with an
EQL query.

**Which profile a game uses:** a `?padprofile=<name>` URL override; otherwise a
profile naming the game whose `padMatch` matches the pad; one naming the game;
a global profile (empty `games`) matching the pad; any global profile; or the
built-in default.

| Field | Meaning |
|---|---|
| `games` | Game names (e.g. `snake`, `polybius`). Empty means every game |
| `padMatch` | Text found in the browser's pad id (e.g. `0f0d`), case-insensitive. Empty means any pad |
| `fourWay` | Only the newest direction is held, so diagonals can't occur. Use it for grid games |
| `deadzonePercent` | How far an axis must move to count as pressed (10–90, default 50) |
| `expectStandardMapping` | Show a hint when the pad isn't in X-Input/standard mode |
| `players[].pad` | Browser gamepad index, 0–3 |
| `players[].bindings[]` | `input`, `key`, and `mode` (`hold`, or `tap` for one press, as used for pause) |

## Dependencies

None.

## Referenced resources

None.

## Examples

/// tab | YAML

```yaml
-{{ include_snippet(resource_name) }}-
```

///
