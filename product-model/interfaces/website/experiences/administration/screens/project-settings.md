---
{
  "entities": [
    {
      "entity": "project",
      "shows": [
        "Project ID",
        "Name",
        "Visibility",
        "Entities",
        "Metric display",
        "Dimension display"
      ],
      "collects": [
        "Name",
        "Visibility",
        "Entities",
        "Metric display",
        "Dimension display"
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
      "target": "packages/web/src/components/settings/projects/index.tsx"
    }
  ]
}
---

# Project settings

One Project’s immutable ID, name, visibility, Entity associations and metric/dimension display policy, including Auto, Always and Hidden selections.
