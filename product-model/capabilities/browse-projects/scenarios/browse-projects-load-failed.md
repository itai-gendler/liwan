---
{
  "kind": "edge",
  "routes": {
    "p": "P — projects",
    "a-projects": "A — projects",
    "a-project-list": "A — project list"
  },
  "steps": [
    {
      "text": "The User opens discovery with the selected metric and range",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::projects"
        },
        "a-projects": {
          "place": "website::account::projects"
        },
        "a-project-list": {
          "place": "website::account::project-list"
        }
      }
    },
    {
      "text": "The requested storage operation cannot complete.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::projects"
        },
        "a-projects": {
          "place": "website::account::projects"
        },
        "a-project-list": {
          "place": "website::account::project-list"
        }
      }
    },
    {
      "text": "The client exposes a failed load rather than a successful result; no completed aggregate save or carrying navigation is promised.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "p": {
          "place": "website::public::projects"
        },
        "a-projects": {
          "place": "website::account::projects"
        },
        "a-project-list": {
          "place": "website::account::project-list"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/dashboard.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/projects.rs"
    }
  ]
}
---

# Browse Projects — load failed

## Trigger

The requested storage operation cannot complete.

## Outcome

The client exposes a failed load rather than a successful result; no completed aggregate save or carrying navigation is promised.
