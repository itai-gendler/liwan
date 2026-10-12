---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "changes",
      "facts": [
        "Local credential"
      ],
      "contexts": [
        {
          "place": "website::account"
        }
      ]
    }
  ],
  "permits": [
    {
      "related": [
        {
          "verb": "identifies",
          "entity": "user"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "identifies",
          "entity": "administrator"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/auth.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/users.rs"
    }
  ]
}
---

# Users and Administrators change only their identified own local credential

The targeted Account must be identified by the acting User or Administrator. Current-password verification and new-password validation are separate requirements before guarded replacement.
