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

# Only Administrators change Team members through Website administration

The acting Administrator edits the selected Account’s Teams or the selected Team’s members; validated memberships are saved in both directions.
