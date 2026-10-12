---
{
  "kind": "primary",
  "routes": {
    "r": "R — api key settings"
  },
  "steps": [
    {
      "text": "The Administrator confirms deletion of the selected batch credential",
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
      "text": "Deletion of the selected key is confirmed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::api-key-settings"
        }
      }
    },
    {
      "text": "Its credential and configuration are removed and cease authenticating; the caller is carried to the remaining-key list.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "api-key",
          "effect": "removes"
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

# Delete API Key — deleted and carried

## Trigger

Deletion of the selected key is confirmed.

## Outcome

Its credential and configuration are removed and cease authenticating; the caller is carried to the remaining-key list.
