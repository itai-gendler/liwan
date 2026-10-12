---
{
  "kind": "validation",
  "routes": {
    "r-project-settings": "R — project settings",
    "r-entity-settings": "R — entity settings"
  },
  "steps": [
    {
      "text": "The User selects an existing source association for removal",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "r-project-settings": {
          "place": "website::administration::project-settings"
        },
        "r-entity-settings": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "A valid dashboard session resolves to the ordinary role when this administration request is attempted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r-project-settings": {
          "place": "website::administration::project-settings"
        },
        "r-entity-settings": {
          "place": "website::administration::entity-settings"
        }
      }
    },
    {
      "text": "The request returns Forbidden (403) before protected settings are disclosed or the requested administrative operation is performed.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "r-project-settings": {
          "place": "website::administration::project-settings"
        },
        "r-entity-settings": {
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
      "target": "crates/liwan/src/app/core/projects.rs"
    }
  ]
}
---

# Remove Entity from Project — access rejected

## Trigger

A valid dashboard session resolves to the ordinary User role when this administration request is attempted.

## Outcome

The request returns Forbidden (403) before protected settings are disclosed or the requested administrative operation is performed.

## Edge cases

- A missing or invalid dashboard session returns Unauthorized (401) before this operation; malformed browser credential pairs are cleared.
