---
{
  "kind": "edge",
  "routes": {
    "r": "R — user settings"
  },
  "steps": [
    {
      "text": "The Administrator opens the selected identity’s settings",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
        }
      }
    },
    {
      "text": "The requested subject does not exist.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::user-settings"
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
          "place": "website::administration::user-settings"
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

# View User settings — missing user

## Trigger

The requested subject does not exist.

## Outcome

The missing-subject result is returned, with no successful edit or invented subject.
