---
{
  "kind": "primary",
  "routes": {
    "c": "C"
  },
  "steps": [
    {
      "text": "The Operator requests application of current retention and disabled-data policy",
      "kind": "actor",
      "actor": "operator",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "Pruning is requested against current registered-source policy.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "Events strictly older than each applicable cutoff are deleted; disabled attribution/location/session data is cleared as applicable",
      "kind": "product",
      "actor": "operator",
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
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "The Product changes the selected Pageview; changes the selected named occurrence",
      "kind": "product",
      "actor": "operator",
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
        "c": {
          "place": "liwan-cli"
        }
      }
    },
    {
      "text": "Events strictly older than each applicable cutoff are deleted; disabled attribution/location/session data is cleared as applicable. Per-source totals are returned; no historical host/drop filtering or regrouping occurs.",
      "kind": "product",
      "actor": "operator",
      "entities": [],
      "contexts": {
        "c": {
          "place": "liwan-cli"
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

# Prune events — cli pruned

## Trigger

Pruning is requested against current registered-source policy.

## Outcome

Events strictly older than each applicable cutoff are deleted; disabled attribution/location/session data is cleared as applicable. Per-source totals are returned; no historical host/drop filtering or regrouping occurs.
