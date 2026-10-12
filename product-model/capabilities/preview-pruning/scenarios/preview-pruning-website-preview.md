---
{
  "kind": "primary",
  "routes": {
    "r": "R — collection"
  },
  "steps": [
    {
      "text": "The Administrator requests a dry run under current retention and disabled-data settings",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::collection"
        }
      }
    },
    {
      "text": "A dry-run pruning request uses current registered-source policy.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::collection"
        }
      }
    },
    {
      "text": "Per-source deletion and clearing counts are returned without event mutation. Counts reflect the preview’s current data and policy and need not match a later application.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "pageview",
          "effect": "reads",
          "facts": [
            "Entity ID",
            "Recorded at",
            "Visitor group",
            "Hostname",
            "Path",
            "Referrer",
            "Platform",
            "Browser",
            "Mobile",
            "Country",
            "City",
            "Campaign attribution",
            "Screen width",
            "Orientation",
            "Properties",
            "Pageview timing",
            "Exit time"
          ]
        },
        {
          "entity": "custom-event",
          "effect": "reads",
          "facts": [
            "Entity ID",
            "Recorded at",
            "Visitor group",
            "Hostname",
            "Path",
            "Referrer",
            "Platform",
            "Browser",
            "Mobile",
            "Country",
            "City",
            "Campaign attribution",
            "Screen width",
            "Orientation",
            "Properties",
            "Event name"
          ]
        },
        {
          "entity": "entity",
          "effect": "reads",
          "facts": [
            "Entity ID",
            "Effective collection settings"
          ]
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::collection"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/web/routes/admin.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/app/core/events.rs"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crates/liwan/src/cli.rs"
    }
  ]
}
---

# Preview pruning — website preview

## Trigger

A dry-run pruning request uses current registered-source policy.

## Outcome

Per-source deletion and clearing counts are returned without event mutation. Counts reflect the preview’s current data and policy and need not match a later application.
