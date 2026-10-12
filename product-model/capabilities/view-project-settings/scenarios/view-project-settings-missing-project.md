---
{
  "kind": "edge",
  "routes": {
    "r": "R — project settings"
  },
  "steps": [
    {
      "text": "The Administrator opens the selected grouping editor",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::project-settings"
        }
      }
    },
    {
      "text": "The requested subject does not exist.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::project-settings"
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
          "place": "website::administration::project-settings"
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
      "target": "crates/liwan/src/app/core/projects.rs"
    }
  ]
}
---

# View Project settings — missing project

## Trigger

The requested subject does not exist.

## Outcome

The missing-subject result is returned, with no successful edit or invented subject.
