---
{
  "kind": "primary",
  "routes": {
    "r": "R — api keys"
  },
  "steps": [
    {
      "text": "The Administrator opens batch-credential metadata",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::api-keys"
        }
      }
    },
    {
      "text": "The key list is requested.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::api-keys"
        }
      }
    },
    {
      "text": "Key identity, name and lifecycle metadata are returned. Existing stored secrets cannot be retrieved; selected configuration is available through the key editor.",
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
          "place": "website::administration::api-keys"
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

# Browse API Keys — metadata list

## Trigger

The key list is requested.

## Outcome

Key identity, name and lifecycle metadata are returned. Existing stored secrets cannot be retrieved; selected configuration is available through the key editor.
