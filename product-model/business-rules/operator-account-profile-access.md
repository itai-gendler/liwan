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
          "place": "liwan-cli"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "operator"
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

# Only Operators read Account Username, Administrator access

Operators read the selected Account Username, Administrator access in Liwan CLI.
