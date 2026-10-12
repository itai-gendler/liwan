---
{
  "kind": "validation",
  "routes": {
    "r": "R — entity settings"
  },
  "steps": [
    {
      "text": "The Administrator submits source overrides, hostnames or name changes",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "A submitted override value or hostname pattern is invalid.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::entity-settings"
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
          "place": "website::administration::entity-settings"
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
      "target": "crates/liwan/src/app/core/entities.rs"
    }
  ]
}
---

# Change Entities settings — invalid settings or hostname

## Trigger

A submitted override value or hostname pattern is invalid.

## Outcome

The request is refused before successful persistence of the requested change; no success or hand-off is reported.
