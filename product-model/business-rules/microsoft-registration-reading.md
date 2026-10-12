---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "microsoft-registration",
      "effect": "reads",
      "facts": [
        "Client ID",
        "Secret configured",
        "Callback URL",
        "Tenant"
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

# Only Administrators read Microsoft registration Client ID, Secret configured, Callback URL, Tenant

Administrators read the selected Microsoft registration Client ID, Secret configured, Callback URL, Tenant in Website administration.
