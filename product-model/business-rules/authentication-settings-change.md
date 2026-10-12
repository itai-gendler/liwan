---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "authentication-settings",
      "effect": "changes",
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

# Only Administrators change Authentication settings

Administrators change the selected Authentication settings in Website administration.
