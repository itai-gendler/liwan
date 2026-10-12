---
{
  "kind": "primary",
  "routes": {
    "r": "R — api key settings"
  },
  "steps": [
    {
      "text": "The Administrator removes a selected direct-source entry",
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
      "text": "A selected direct-source entry is removed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::api-key-settings"
        }
      }
    },
    {
      "text": "That entry is removed; effective source access can remain through all direct scope or a scoped grouping.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "api-key",
          "effect": "changes",
          "facts": [
            "Entities"
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

# Remove Entity from API Key — removed from direct scope

## Trigger

A selected direct-source entry is removed.

## Outcome

That entry is removed; effective source access can remain through all direct scope or a scoped grouping.
