---
{
  "kind": "validation",
  "routes": {
    "r": "R — authentication"
  },
  "steps": [
    {
      "text": "The User removes the selected provider-group mapping",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "A valid dashboard session resolves to the ordinary role when this administration request is attempted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    },
    {
      "text": "The request returns Forbidden (403) before protected settings are disclosed or the requested administrative operation is performed.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::authentication"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/external_auth.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/external_auth/mod.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/auth/index.tsx"
    }
  ]
}
---

# Remove Team mapping — access rejected

## Trigger

A valid dashboard session resolves to the ordinary User role when this administration request is attempted.

## Outcome

The request returns Forbidden (403) before protected settings are disclosed or the requested administrative operation is performed.

## Edge cases

- A missing or invalid dashboard session returns Unauthorized (401) before this operation; malformed browser credential pairs are cleared.
