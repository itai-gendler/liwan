---
{
  "kind": "primary",
  "routes": {
    "r": "R — api key settings"
  },
  "steps": [
    {
      "text": "The Administrator adds an existing grouping to selected following scope",
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
      "text": "An existing grouping is selected under selected grouping scope.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::api-key-settings"
        }
      }
    },
    {
      "text": "It is added to grouping-following scope, which includes its current associated sources.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "api-key",
          "effect": "changes",
          "facts": [
            "Projects"
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

# Add Project to API Key — added to project scope

## Trigger

An existing grouping is selected under selected Project scope.

## Outcome

It is added to Project-following scope, which includes its current associated sources.
