---
{
  "kind": "validation",
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
      "text": "The key name, selected scope references, expiry or permission vocabulary violates validation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::api-keys"
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

# Create API Key — invalid name scope or permission

## Trigger

The key name, selected scope references, expiry or permission vocabulary violates validation.

## Outcome

The request is refused before successful persistence of the requested change; no success or hand-off is reported.
