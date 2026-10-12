---
{
  "kind": "validation",
  "routes": {
    "r": "R — team settings"
  },
  "steps": [
    {
      "text": "The User removes a selected grouping-access entry",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "A valid dashboard session resolves to the ordinary role when this administration request is attempted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
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
          "place": "website::administration::team-settings"
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
      "target": "crates/liwan/src/app/core/teams.rs"
    }
  ]
}
---

# Remove Project from Team — access rejected

## Trigger

A valid dashboard session resolves to the ordinary User role when this administration request is attempted.

## Outcome

The request returns Forbidden (403) before protected settings are disclosed or the requested administrative operation is performed.

## Edge cases

- A missing or invalid dashboard session returns Unauthorized (401) before this operation; malformed browser credential pairs are cleared.
