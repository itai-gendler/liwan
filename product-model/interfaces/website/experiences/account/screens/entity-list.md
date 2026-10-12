---
{
  "entities": [
    {
      "entity": "entity",
      "shows": [
        "Entity ID",
        "Name",
        "Projects"
      ],
      "collects": [
        "Entity ID",
        "Name"
      ]
    },
    {
      "entity": "project",
      "shows": [
        "Project ID",
        "Name",
        "Visibility"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/entities/dialogs.tsx"
    }
  ]
}
---

# Entity list

Entity discovery shows source IDs, names and associated visible Projects, with new-source ID and name inputs.
