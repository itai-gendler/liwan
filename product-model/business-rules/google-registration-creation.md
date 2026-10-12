---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "google-registration",
      "effect": "creates",
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

# Only Administrators create Google registration

Administrators create the selected Google registration in Website administration.
