---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "openid-connect-registration",
      "effect": "reads",
      "facts": [
        "Client ID",
        "Secret configured",
        "Callback URL",
        "Issuer URL",
        "Sign-in label",
        "Additional scopes",
        "Group claim"
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

# Only Administrators read OpenID Connect registration Client ID, Secret configured, Callback URL, Issuer URL, Sign-in label, Additional scopes, Group claim

Administrators read the selected OpenID Connect registration Client ID, Secret configured, Callback URL, Issuer URL, Sign-in label, Additional scopes, Group claim in Website administration.
