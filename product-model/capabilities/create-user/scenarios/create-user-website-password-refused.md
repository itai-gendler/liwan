---
{
  "kind": "validation",
  "routes": {
    "r": "R — users"
  },
  "steps": [
    {
      "text": "The Administrator supplies username, password and the selected shipped role",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::users"
        }
      }
    },
    {
      "text": "The submitted Website password violates the form or handler minimum.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::users"
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
          "place": "website::administration::users"
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
      "target": "crates/liwan/src/app/core/users.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/cli.rs"
    }
  ]
}
---

# Create User — website password refused

## Trigger

The submitted Website password violates the form or handler minimum.

## Outcome

The request is refused before successful persistence of the requested change; no success or hand-off is reported.
