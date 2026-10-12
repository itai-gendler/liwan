---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "team",
      "effect": "changes",
      "facts": [
        "Members"
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
      "target": "crates/liwan/src/web/routes/admin.rs"
    }
  ]
}
---

# Visitors add initial membership for a new external Account only through configured external signup

This single conjunctive grant binds the acting Visitor’s newly created external Account, the exact saved Authentication settings and the actual initial assignment operation. External sign-in and New user creation must be enabled. Only the existing Default Team or Teams selected by exact matched provider-group mappings qualify. It never edits an existing Account’s memberships, resynchronizes an existing external identity or grants an unrelated Team.
