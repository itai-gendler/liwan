---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "reads",
      "facts": [
        "Username",
        "Administrator access"
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

# Users and Administrators read only their identified own Account profile

The targeted Account must be identified by the acting User or Administrator. Only its Username and Administrator access are disclosed in My account; credentials are not read.
