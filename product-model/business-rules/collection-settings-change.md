---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "collection-settings",
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

# Only Administrators change Collection settings

Administrators change the selected Collection settings in Website administration.
