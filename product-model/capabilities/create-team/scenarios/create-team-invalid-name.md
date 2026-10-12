---
{
  "kind": "validation",
  "routes": {
    "r": "R — teams"
  },
  "steps": [
    {
      "text": "The Administrator supplies a new membership-group name",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::teams"
        }
      }
    },
    {
      "text": "The submitted trimmed name is blank.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::teams"
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
          "place": "website::administration::teams"
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

# Create Team — invalid name

## Trigger

The submitted trimmed name is blank.

## Outcome

The request is refused before successful persistence of the requested change; no success or hand-off is reported.
