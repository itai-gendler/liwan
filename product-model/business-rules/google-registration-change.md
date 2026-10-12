---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "google-registration",
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

# Only Administrators change Google registration

Administrators change the selected Google registration in Website administration.
