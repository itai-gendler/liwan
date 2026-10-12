---
{
  "kind": "primary",
  "routes": {
    "r": "R — api key settings"
  },
  "steps": [
    {
      "text": "The Administrator opens the selected batch-credential editor",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::api-key-settings"
        }
      }
    },
    {
      "text": "The selected key exists.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::api-key-settings"
        }
      }
    },
    {
      "text": "Name, direct and grouping-following scope, supported permission, creation/expiry and last-use metadata are shown without retrieving its existing secret.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "api-key",
          "effect": "reads",
          "facts": [
            "Key ID",
            "Name",
            "Permissions",
            "Entity access mode",
            "Entities",
            "Project access mode",
            "Projects",
            "Created at",
            "Expires at",
            "Last used at"
          ]
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::api-key-settings"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/api_keys.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/api-keys.tsx"
    }
  ]
}
---

# View API Key settings — selected key

## Trigger

The selected key exists.

## Outcome

Name, direct and Project-following scope, supported permission, creation/expiry and last-use metadata are shown without retrieving its existing secret.
