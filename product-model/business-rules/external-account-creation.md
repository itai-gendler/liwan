---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "creates",
      "contexts": [
        {
          "place": "website::public::sign-in"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "visitor"
      ],
      "configuredBy": "authentication-settings",
      "when": [
        {
          "entity": "authentication-settings",
          "fact": "External sign-in enabled",
          "is": true
        },
        {
          "entity": "authentication-settings",
          "fact": "New user creation",
          "is": true
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

# Visitors create external Accounts only when saved external signup is enabled

The saved singleton Authentication settings must enable external sign-in and New user creation. The valid provider identity must be previously unbound; initial Team assignments follow that exact saved signup configuration.
