---
resource_name: PolybiusScore
resource_name_plural: polybiusscores
resource_name_plural_title: Polybius Scores
resource_name_acronym: PS
crd_path: docs/polybius.cdoyle.dev/crds/polybius.cdoyle.dev_polybiusscores.yaml
# 'auto-crd' will automatically select between the normal resource and workflow icon
icon: auto-crd
---

# Polybius Scores

-{{% import 'icons.html' as icons %}}-

-{{ category(resource_name_plural) }}- → -{{ icons.circle(letter=resource_name_acronym, text=resource_name_plural_title) }}-

One finished run of the game: one leaderboard entry. The game creates one when a player enters their name after a run. It ranks every score in the score namespace, highest first; equal scores are ranked by the earlier `recordedAt`. Nothing reconciles a PolybiusScore, so deleting one simply removes that entry from the board.

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
