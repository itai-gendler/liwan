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
          "place": "website::administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
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

# Only Administrators read Account Username, Administrator access

Administrators read the selected Account Username, Administrator access in Website administration.
