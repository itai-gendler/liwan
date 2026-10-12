---
{
  "kind": "validation",
  "routes": {
    "c": "C"
  },
  "steps": [
    {
      "text": "The Operator supplies username, password and the selected shipped role",
      "kind": "actor",
      "actor": "operator",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "The submitted name has a character other than a Unicode alphanumeric, hyphen or underscore, or its UTF-8 length is outside 2–64 bytes.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "Core validation returns an invalid-username error; no identity record is inserted and CLI creation reports no success.",
      "kind": "product",
      "actor": "operator",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
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
      "target": "crates/liwan/src/utils/validate.rs#is_valid_username"
    }
  ]
}
---

# Create User — invalid username — cli

## Trigger

The submitted name has a character other than a Unicode alphanumeric, hyphen or underscore, or its UTF-8 length is outside 2–64 bytes.

## Outcome

Core validation returns an invalid-username error; no identity record is inserted and CLI creation reports no success.
