---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "google-registration",
      "effect": "removes",
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

# Only Administrators remove Google registration

Administrators remove the selected Google registration in Website administration.
