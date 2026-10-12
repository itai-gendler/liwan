---
{
  "entities": [
    {
      "entity": "collection-settings",
      "shows": [
        "Visitor grouping",
        "Session collection",
        "Campaign collection",
        "Location detail",
        "History retention",
        "Drop rules"
      ],
      "collects": [
        "Visitor grouping",
        "Session collection",
        "Campaign collection",
        "Location detail",
        "History retention",
        "Drop rules"
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
      "target": "packages/web/src/components/settings/collection/index.tsx"
    }
  ]
}
---

# Collection

Global collection policy and Drop-rule editing, plus pruning requests and preview/application results.
