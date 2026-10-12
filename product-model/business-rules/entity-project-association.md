---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "entity",
      "effect": "changes",
      "facts": [
        "Projects"
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

# Only Administrators change Entity Projects

Administrators change the selected Entity Projects in Website administration.
