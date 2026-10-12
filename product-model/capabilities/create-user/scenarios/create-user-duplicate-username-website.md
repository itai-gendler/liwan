---
{
  "kind": "edge",
  "routes": {
    "r": "R — users"
  },
  "steps": [
    {
      "text": "The Administrator supplies username, password and the selected shipped role",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::users"
        }
      }
    },
    {
      "text": "The submitted form-valid name becomes an existing username after Unicode lowercasing.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::users"
        }
      }
    },
    {
      "text": "The handler returns 500 with a creation error; the Website presents the error without a creation success or replacement of the existing identity record.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::users"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/cli.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/users/dialogs.tsx"
    }
  ]
}
---

# Create User — duplicate username — website

## Trigger

The submitted form-valid name becomes an existing username after Unicode lowercasing.

## Outcome

The handler reports Failed to create user with 500; the Website presents the error without a creation success or replacement of the existing identity record.
