---
resource_name: PolybiusEvent
resource_name_plural: polybiusevents
resource_name_plural_title: Polybius Telemetry
resource_name_acronym: PE
crd_path: docs/polybius.cdoyle.dev/crds/polybius.cdoyle.dev_polybiusevents.yaml
# 'auto-crd' will automatically select between the normal resource and workflow icon
icon: auto-crd
---

# Polybius Telemetry

-{{% import 'icons.html' as icons %}}-

-{{ category(resource_name_plural) }}- → -{{ icons.circle(letter=resource_name_acronym, text=resource_name_plural_title) }}-

One moment of play worth seeing in a log: a game started, a sector reached, an achievement, an interrogation, the subject's loss, the island, the hatch. The game writes them as it is played, for the telemetry page (`/core/httpproxy/v1/polybius/telemetry.html`) or this table sorted by name, which puts the newest first.

Nothing reconciles a PolybiusEvent. The game deletes the oldest once there are more than `eventKeep` (PolybiusConfig, default 200). Delete them all to clear the log. Set `telemetry: false` in PolybiusConfig to stop writing them.

## Examples

/// tab | YAML

```yaml
-{{ include_snippet(resource_name) }}-
```

///

/// tab | `kubectl`

```bash
cat << 'EOF' | kubectl apply -f -
-{{ include_snippet(resource_name) }}-
EOF
```

///

## Custom Resource Definition

To browse the Custom Resource Definition go to [crd.eda.dev](https://crd.eda.dev/-{{ resource_name_plural }}-.-{{ app_group }}-/-{{ app_api_version }}-).

-{{ crd_viewer(crd_path, collapsed=False) }}-
