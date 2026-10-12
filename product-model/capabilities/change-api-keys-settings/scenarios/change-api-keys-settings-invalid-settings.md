---
{
  "kind": "validation",
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
      "text": "Submitted settings violate their supported values or referenced subjects.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::api-key-settings"
        }
      }
    },
    {
      "text": "The request is refused before successful persistence of the requested change; no success or hand-off is reported.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
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

# Change API Keys settings — invalid settings

## Trigger

Submitted settings violate their supported values or referenced subjects.

## Outcome

The request is refused before successful persistence of the requested change; no success or hand-off is reported.
