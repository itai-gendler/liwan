---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "openid-connect-registration",
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

# Only Administrators change OpenID Connect registration

Administrators change the selected OpenID Connect registration in Website administration.
