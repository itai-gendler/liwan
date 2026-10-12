---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "authentication-settings",
      "effect": "reads",
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

# Only Administrators read Authentication settings

Administrators read the selected Authentication settings in Website administration.
