---
{
  "kind": "primary",
  "routes": {
    "r": "R — api keys"
  },
  "steps": [
    {
      "text": "The Administrator supplies a new credential name, scope, permission and expiry",
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
      "text": "A valid key name, supported permission, direct/grouping scope and expiry choice are submitted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::api-keys"
        }
      }
    },
    {
      "text": "A fresh secret is created and revealed once in the creation outcome; only verification material is retained. Scope/configuration metadata is saved and creation remains on the key-list process.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "api-key",
          "effect": "creates",
          "facts": [
            "Key ID",
            "Name",
            "Credential",
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

# Create API Key — created and revealed

## Trigger

A valid key name, supported permission, direct/Project scope and expiry choice are submitted.

## Outcome

A fresh secret is created and revealed once in the creation outcome; only verification material is retained. Scope/configuration metadata is saved and creation remains on the key-list process.
