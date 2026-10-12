---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "authentication-settings",
      "effect": "reads",
      "facts": [
        "External sign-in enabled",
        "Provider"
      ],
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
        "visitor",
        "user",
        "administrator"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    }
  ]
}
---

# Only Visitors or Users or Administrators read Authentication settings External sign-in enabled, Provider

Visitors or Users or Administrators read the selected Authentication settings External sign-in enabled, Provider in sign in.
