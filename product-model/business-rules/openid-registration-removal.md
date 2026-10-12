---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "openid-connect-registration",
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

# Only Administrators remove OpenID Connect registration

Administrators remove the selected OpenID Connect registration in Website administration.
