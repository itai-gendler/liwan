---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "google-registration",
      "effect": "reads",
      "facts": [
        "Client ID",
        "Secret configured",
        "Callback URL",
        "Workspace domain"
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

# Only Administrators read Google registration Client ID, Secret configured, Callback URL, Workspace domain

Administrators read the selected Google registration Client ID, Secret configured, Callback URL, Workspace domain in Website administration.
