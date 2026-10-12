---
{
  "kind": "edge",
  "routes": {
    "r": "R — team settings"
  },
  "steps": [
    {
      "text": "The Administrator opens the selected membership/access editor",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "The requested subject does not exist.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::team-settings"
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

# View Team settings — missing team

## Trigger

The requested subject does not exist.

## Outcome

The missing-subject result is returned, with no successful edit or invented subject.
