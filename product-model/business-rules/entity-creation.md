---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "entity",
      "effect": "creates",
      "contexts": [
        {
          "place": "website::account::entity-list"
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

# Only Administrators create Entity

Administrators create the selected Entity in entity list.
