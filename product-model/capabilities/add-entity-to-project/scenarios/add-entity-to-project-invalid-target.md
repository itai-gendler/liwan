---
{
  "kind": "validation",
  "routes": {
    "r-project-settings": "R — project settings",
    "r-entity-settings": "R — entity settings"
  },
  "steps": [
    {
      "text": "The Administrator selects an existing source to associate with the grouping",
      "kind": "actor",
      "actor": "administrator",
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
      "text": "An association or membership reference does not resolve to an existing subject.",
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
      "text": "The request is refused before successful persistence of the requested change; no success or hand-off is reported.",
      "kind": "product",
      "actor": "administrator",
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

# Add Entity to Project — invalid target

## Trigger

An association or membership reference does not resolve to an existing subject.

## Outcome

The request is refused before successful persistence of the requested change; no success or hand-off is reported.
