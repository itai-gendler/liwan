---
{
  "entities": [
    {
      "entity": "project",
      "shows": [
        "Project ID",
        "Name",
        "Visibility",
        "Entities"
      ],
      "collects": [
        "Project ID",
        "Name",
        "Visibility"
      ]
    },
    {
      "entity": "entity",
      "shows": [
        "Entity ID",
        "Name"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/projects/dialogs.tsx"
    }
  ]
}
---

# Project list

Project discovery shows names, visibility and associated Entities, with new-Project ID, name and visibility inputs.
