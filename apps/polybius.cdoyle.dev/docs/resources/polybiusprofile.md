---
resource_name: PolybiusProfile
resource_name_plural: polybiusprofiles
resource_name_plural_title: Polybius Profiles
resource_name_acronym: PP
crd_path: docs/polybius.cdoyle.dev/crds/polybius.cdoyle.dev_polybiusprofiles.yaml
# 'auto-crd' will automatically select between the normal resource and workflow icon
icon: auto-crd
---

# Polybius Profiles

-{{% import 'icons.html' as icons %}}-

-{{ category(resource_name_plural) }}- → -{{ icons.circle(letter=resource_name_acronym, text=resource_name_plural_title) }}-

One EDA user's saved progress: achievements, unlocked modes, question decks and play time. The game creates it the first time a user plays and updates it as they unlock things. Writes are grouped, so ordinary play does not create a stream of transactions. The summary fields are for reading in the EDA UI; the game restores from `spec.state`. Delete a profile to reset that user.

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
