---
{
  "kind": "primary",
  "routes": {
    "r": "R — api key settings"
  },
  "steps": [
    {
      "text": "The Administrator submits credential name, scope-mode or permission changes",
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
      "text": "Valid key name, direct/grouping scope mode or supported permission selections are submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::api-key-settings"
        }
      }
    },
    {
      "text": "The named configuration facts are saved. Current grouping membership determines grouping-following effective source scope; existing credentials are not newly disclosed.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "api-key",
          "effect": "changes",
          "facts": [
            "Name",
            "Entity access mode",
            "Project access mode",
            "Permissions"
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

# Change API Keys settings — name modes or permission saved

## Trigger

Valid key name, direct/Project scope mode or supported permission selections are submitted.

## Outcome

The named configuration facts are saved. Current grouping membership determines Project-following effective source scope; existing credentials are not newly disclosed.
