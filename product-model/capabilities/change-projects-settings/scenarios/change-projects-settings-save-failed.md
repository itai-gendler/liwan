---
{
  "kind": "edge",
  "routes": {
    "r": "R — project settings"
  },
  "steps": [
    {
      "text": "The Administrator submits the selected grouping settings",
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
      "text": "The requested storage operation cannot complete.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::project-settings"
        }
      }
    },
    {
      "text": "The client exposes a failed save rather than a successful result; no completed aggregate save or carrying navigation is promised.",
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

# Change Projects settings — save failed

## Trigger

The requested storage operation cannot complete.

## Outcome

The client exposes a failed save rather than a successful result; no completed aggregate save or carrying navigation is promised.
