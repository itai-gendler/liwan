---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "web": "Website"
  },
  "steps": [
    {
      "text": "The Administrator confirms deletion of the selected batch credential",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::api-key-settings"
        }
      },
      "capability": "delete-api-key"
    },
    {
      "text": "Deletion of the selected key is confirmed.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::api-key-settings"
        }
      },
      "capability": "delete-api-key"
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
        "web": {
          "place": "website::administration::api-key-settings"
        }
      },
      "capability": "delete-api-key"
    },
    {
      "text": "The Product carries the caller to the remaining-key metadata list",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "capability": "delete-api-key",
      "contexts": {
        "web": {
          "place": "website::administration::api-key-settings"
        }
      }
    },
    {
      "text": "The Administrator opens batch-credential metadata",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::api-keys"
        }
      },
      "capability": "browse-api-keys"
    },
    {
      "text": "The key list is requested.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "web": {
          "place": "website::administration::api-keys"
        }
      },
      "capability": "browse-api-keys"
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
        "web": {
          "place": "website::administration::api-keys"
        }
      },
      "capability": "browse-api-keys"
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

# Api key removal review — remaining keys

## Trigger

Remove a batch credential and inspect remaining keys.

## Outcome

The key stops authenticating and remaining-key metadata is read.
