---
{
  "kind": "validation",
  "routes": {
    "r-user-settings": "R — user settings",
    "r-team-settings": "R — team settings"
  },
  "steps": [
    {
      "text": "The Administrator selects an identity to add to the membership group",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r-user-settings": {
          "place": "website::administration::user-settings"
        },
        "r-team-settings": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "An association or membership reference does not resolve to an existing subject.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r-user-settings": {
          "place": "website::administration::user-settings"
        },
        "r-team-settings": {
          "place": "website::administration::team-settings"
        }
      }
    },
    {
      "text": "The request is refused before successful persistence of the requested change; no success or hand-off is reported.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r-user-settings": {
          "place": "website::administration::user-settings"
        },
        "r-team-settings": {
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
      "target": "crates/liwan/src/app/core/users.rs"
    }
  ]
}
---

# Add User to Team — invalid target

## Trigger

An association or membership reference does not resolve to an existing subject.

## Outcome

The request is refused before successful persistence of the requested change; no success or hand-off is reported.
