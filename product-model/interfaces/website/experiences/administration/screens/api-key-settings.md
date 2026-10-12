---
{
  "entities": [
    {
      "entity": "api-key",
      "shows": [
        "Key ID",
        "Name",
        "Permissions",
        "Entity access mode",
        "Entities",
        "Project access mode",
        "Projects",
        "Created at",
        "Expires at",
        "Last used at",
        "Credential"
      ],
      "collects": [
        "Name",
        "Permissions",
        "Entity access mode",
        "Entities",
        "Project access mode",
        "Projects",
        "Expires at"
      ]
    },
    {
      "entity": "entity",
      "shows": [
        "Entity ID",
        "Name"
      ]
    },
    {
      "entity": "project",
      "shows": [
        "Project ID",
        "Name",
        "Visibility",
        "Entities"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/api-keys.tsx"
    }
  ]
}
---

# API Key settings

One key’s configuration and regeneration outcome. A replacement secret is shown only after regeneration.
