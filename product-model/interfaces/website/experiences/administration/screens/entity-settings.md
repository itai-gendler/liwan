---
{
  "entities": [
    {
      "entity": "entity",
      "shows": [
        "Entity ID",
        "Name",
        "Projects",
        "Visitor grouping",
        "Session collection",
        "Campaign collection",
        "Location detail",
        "History retention",
        "Allowed hostnames",
        "Drop rules",
        "Effective collection settings",
        "Custom-data presence",
        "Tracking snippet"
      ],
      "collects": [
        "Name",
        "Projects",
        "Visitor grouping",
        "Session collection",
        "Campaign collection",
        "Location detail",
        "History retention",
        "Allowed hostnames",
        "Drop rules"
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
    },
    {
      "entity": "drop-rule",
      "shows": [
        "Scope",
        "Conditions"
      ],
      "collects": [
        "Conditions"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "packages/web/src/components/settings/entities/index.tsx"
    }
  ]
}
---

# Entity settings

One Entity’s immutable ID, name, Project associations, collection overrides, allowed hostnames, Drop rules and tracking snippet. Inherited values resolve against global collection settings.
