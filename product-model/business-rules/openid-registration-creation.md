---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "openid-connect-registration",
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

# Only Administrators create OpenID Connect registration

Administrators create the selected OpenID Connect registration in Website administration.
