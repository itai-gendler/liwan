---
{
  "kind": "validation",
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
      "text": "The entered username fails the Website requirement of 2–20 ASCII letters, digits, hyphens or underscores.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::users"
        }
      }
    },
    {
      "text": "Form validation prevents creation submission; no identity record is created and no successful creation is reported.",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/utils/validate.rs#is_valid_username"
    }
  ]
}
---

# Create User — invalid username — website

## Trigger

The entered username fails the Website requirement of 2–20 ASCII letters, digits, hyphens or underscores.

## Outcome

Form validation prevents creation submission; no identity record is created and no successful creation is reported.

## Edge cases

- A request reaching the handler directly is checked by the core 2–64 UTF-8-byte validator with Unicode alphanumeric, hyphen and underscore characters; a core-invalid name produces Failed to create user with 500, without inserting an account.
