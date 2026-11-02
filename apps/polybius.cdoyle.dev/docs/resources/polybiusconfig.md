---
resource_name: PolybiusConfig
resource_name_plural: polybiusconfigs
resource_name_plural_title: Polybius Config
resource_name_acronym: PC
crd_path: docs/polybius.cdoyle.dev/crds/polybius.cdoyle.dev_polybiusconfigs.yaml
# 'auto-crd' will automatically select between the normal resource and workflow icon
icon: auto-crd
---

# Polybius Config

-{{% import 'icons.html' as icons %}}-

-{{ category(resource_name_plural) }}- → -{{ icons.circle(letter=resource_name_acronym, text=resource_name_plural_title) }}-

Optional settings for the game. With none, the defaults apply. The game reads the first PolybiusConfig it finds, so create one named `default` in the `eda` namespace. Changes apply the next time the game page loads.

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
