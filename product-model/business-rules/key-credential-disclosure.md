---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "api-key",
      "effect": "reads",
      "facts": [
        "Credential"
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

# Only Administrators read API Key Credential

Administrators read the selected API Key Credential in Website administration. Only the fresh secret returned by creation or regeneration is disclosed; the stored secret cannot be retrieved.
