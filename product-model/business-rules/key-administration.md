---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "api-key",
      "effect": "changes",
      "facts": [
        "Name",
        "Credential",
        "Permissions",
        "Entity access mode",
        "Entities",
        "Project access mode",
        "Projects",
        "Expires at",
        "Last used at"
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

# Only Administrators change API Key configuration and regenerate credentials

An Administrator changes the selected key’s name, supported permission, direct or Project-following scope, or regeneration credential and expiry in Website administration. Regeneration clears Last used at and retains Created at. Last used at is not an editable input; successful key authentication in server collection records it independently.
