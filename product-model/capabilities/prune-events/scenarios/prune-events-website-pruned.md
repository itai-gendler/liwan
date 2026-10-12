---
{
  "kind": "primary",
  "routes": {
    "r": "R — collection"
  },
  "steps": [
    {
      "text": "The Administrator requests application of current retention and disabled-data policy",
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
      "text": "Pruning is requested against current registered-source policy.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "r": {
          "place": "website::administration::collection"
        }
      }
    },
    {
      "text": "Events strictly older than each applicable cutoff are deleted; disabled attribution/location/session data is cleared as applicable",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "pageview",
          "effect": "removes"
        },
        {
          "entity": "custom-event",
          "effect": "removes"
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::collection"
        }
      }
    },
    {
      "text": "The Product changes the selected Pageview; changes the selected named occurrence",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "pageview",
          "effect": "changes",
          "facts": [
            "Campaign attribution",
            "Country",
            "City",
            "Pageview timing",
            "Exit time"
          ]
        },
        {
          "entity": "custom-event",
          "effect": "changes",
          "facts": [
            "Campaign attribution",
            "Country",
            "City"
          ]
        }
      ],
      "contexts": {
        "r": {
          "place": "website::administration::collection"
        }
      }
    },
    {
      "text": "Events strictly older than each applicable cutoff are deleted; disabled attribution/location/session data is cleared as applicable. Per-source totals are returned; no historical host/drop filtering or regrouping occurs.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
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

# Prune events — website pruned

## Trigger

Pruning is requested against current registered-source policy.

## Outcome

Events strictly older than each applicable cutoff are deleted; disabled attribution/location/session data is cleared as applicable. Per-source totals are returned; no historical host/drop filtering or regrouping occurs.
