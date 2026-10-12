---
{
  "kind": "edge",
  "routes": {
    "r": "R — entity settings"
  },
  "steps": [
    {
      "text": "The Administrator opens the selected source settings and snippet",
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
      "text": "The requested subject does not exist.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "The missing-subject result is returned, with no successful edit or invented subject.",
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

# View Entity settings — missing entity

## Trigger

The requested subject does not exist.

## Outcome

The missing-subject result is returned, with no successful edit or invented subject.
